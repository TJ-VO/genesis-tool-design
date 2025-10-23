# Zero-Access Collaboration Architecture

**Status:** Future Vision Document  
**Part of:** [Community Deck](overview.md)

---

## Overview

This document describes the architectural approach for enabling real-time collaboration while maintaining zero-access encryption. It addresses the fundamental challenge: how can multiple users work on shared knowledge without the server ever seeing the content?

**Core Principle:** Collaboration without compromising sovereignty.

---

## The Challenge

### The Fundamental Conflict

**Zero-Access Encryption:**
- Server cannot read user data
- All encryption/decryption happens client-side
- User-controlled keys (PBKDF2 + Fernet)

**Real-Time Collaboration:**
- Multiple users edit shared content
- Changes must be synchronized
- Conflicts must be resolved

**The Problem:** Traditional collaboration tools (operational transformation, last-write-wins) require the server to read and merge content. This breaks zero-access encryption.

---

## The "Conflicted Copy" Problem

### Scenario: Legal Team Collaboration

```
Team shares encrypted sanctuary.db in cloud storage
├─ Lawyer A (offline): Adds 10 messages, creates 2 branches
├─ Lawyer B (offline): Adds 5 messages, edits same branch
└─ Both go online → Sync conflict

Traditional file sync creates:
├─ sanctuary.db
└─ sanctuary (Lawyer A's conflicted copy).db

Result: Two separate knowledge bases, never automatically merged
```

**Why this fails:**
- File sync services see only encrypted blobs
- Cannot merge without reading content
- Creates duplicate files instead

---

## The Solution: Git-Like Architecture

### Core Concept

Instead of storing a monolithic database file, store each message/block as a separate encrypted object (like Git commits).

**Architecture:**

```
Traditional (File-Based):
sanctuary.db (single encrypted file)
└─ Contains all messages, blocks, branches

Git-Like (Object-Based):
sanctuary/
├─ objects/
│   ├─ a3f5b8c2... (encrypted message object)
│   ├─ d9e1f4a7... (encrypted block object)
│   └─ b6c3d8e5... (encrypted branch object)
├─ refs/
│   ├─ heads/main
│   └─ heads/branch-nutrition
└─ index (metadata, not encrypted content)
```

---

## How It Works

### 1. Object Storage

**Each atomic unit becomes an encrypted object:**

```
Message Object (encrypted):
{
  "type": "message",
  "content": "[encrypted]",
  "parent": "a3f5b8c2...",
  "author_signature": "[signed with private key]",
  "timestamp": 1729526400
}

Block Object (encrypted):
{
  "type": "block",
  "topic": "[encrypted]",
  "ranges": [[1,5], [11,15]],
  "messages": ["a3f5b8c2...", "d9e1f4a7..."],
  "author_signature": "[signed]"
}

Branch Object (metadata):
{
  "type": "branch",
  "name": "main",
  "head": "b6c3d8e5...",
  "parent": "f2a9b4c7..."
}
```

**Key Insight:** Only content is encrypted. Metadata (object IDs, parent relationships) remains visible for conflict detection.

---

### 2. Client-Side Conflict Detection

**Workflow:**

```
Step 1: Lawyer A creates Branch A (offline)
├─ Creates new message objects
├─ Signs each with private key
└─ Updates local branch pointer

Step 2: Lawyer B creates Branch B (offline)
├─ Creates new message objects (same parent as A)
├─ Signs each with private key
└─ Updates local branch pointer

Step 3: Both sync to cloud storage
├─ Both push their objects
└─ Conflict detected: Two branches from same parent

Step 4: Client A detects conflict
├─ Downloads Branch B objects (still encrypted)
├─ Decrypts locally
└─ Prepares for merge
```

**Why this works:**
- Server never sees content (only encrypted objects)
- Client detects conflicts by comparing object graphs
- Merging happens client-side after decryption

---

### 3. AI-Powered Semantic Merging

**The Innovation:** Use AI to understand semantic meaning and suggest intelligent merges.

**Traditional Git Merge (Text-Based):**
```
Lawyer A: "File objection due to inadmissible evidence."
Lawyer B: "File objection because evidence is missing."
Git: CONFLICT (cannot merge automatically)
```

**AI-Powered Semantic Merge:**
```
Step 1: Client decrypts both versions
Step 2: AI analyzes semantic meaning
        - Both want to file objection
        - A: Evidence inadmissible
        - B: Evidence missing
Step 3: AI suggests merge:
        "File objection: evidence inadmissible and missing."
Step 4: User reviews and approves
Step 5: Create signed merge commit
```

**Architecture:**

```
Client A (has conflict):
├─ Downloads encrypted Branch B objects
├─ Decrypts locally
├─ Feeds both versions to AI (local or cloud AI with user consent)
├─ AI suggests semantic merge
├─ User approves/edits suggestion
├─ Creates new merge commit
├─ Signs with private key
└─ Pushes to cloud storage
```

**Privacy Options:**
- **Local AI:** Run AI model on user's device (complete privacy)
- **Cloud AI:** Use privacy-focused AI provider (user must consent to sending decrypted content)
- **Manual Merge:** User resolves conflict manually (no AI)

---

### 4. Cryptographic Audit Trail

**Every change is signed:**

```
Merge Commit:
{
  "type": "merge",
  "parents": ["branch_a_head", "branch_b_head"],
  "merged_content": "[encrypted]",
  "signatures": {
    "lawyer_a": "[signature]",
    "lawyer_b": "[signature]"
  },
  "timestamp": 1729526400,
  "merge_strategy": "ai_semantic"
}
```

**Benefits:**
- ✅ Provable authorship (who changed what)
- ✅ Immutable history (cannot be altered)
- ✅ Audit trail (for compliance)
- ✅ Zero-access maintained (server never sees content)

**Optional:** Store commit hashes on blockchain for additional proof (see [blockchain-for-thoughts.md](../06-future/blockchain-for-thoughts.md)).

---

## Team Encryption Keys

### The Multi-Party Problem

**Challenge:** How do team members share encryption keys without the server seeing them?

**Solution: Asymmetric Cryptography**

```
Step 1: Team Creation
├─ Lawyer A creates team workspace
├─ Generates team symmetric key (AES-256)
├─ Encrypts team key with own public key
└─ Stores encrypted team key in cloud

Step 2: Invite Lawyer B
├─ Lawyer A encrypts team key with B's public key
├─ Sends encrypted key via secure channel (e.g., encrypted email)
├─ Lawyer B decrypts with private key
└─ Both now have team symmetric key

Step 3: Collaborative Work
├─ Both encrypt/decrypt team content with shared symmetric key
├─ Sign individual changes with private keys
└─ Server never sees symmetric key or content
```

**Key Exchange Options:**
- Encrypted email (e.g., PGP/GPG)
- QR code (in-person exchange)
- Secure messaging (e.g., Signal Protocol)
- Password-protected link (PAKE protocol)

---

## Key Revocation

### The Challenge

**Scenario:** Lawyer C leaves the team. How do we revoke access without re-encrypting everything?

**Solution: Key Rotation + Forward Secrecy**

```
Step 1: Generate New Team Key
├─ Lawyer A generates new symmetric key
└─ Shares with remaining team members (Lawyer B)

Step 2: Re-encrypt Future Content
├─ New objects encrypted with new key
└─ Old objects remain encrypted with old key

Step 3: Access Control
├─ Lawyer C can still read old objects (historical access)
├─ Lawyer C cannot read new objects (revoked access)
└─ Optional: Re-encrypt critical old objects with new key
```

**Trade-offs:**
- ✅ Fast revocation (no full re-encryption needed)
- ✅ Granular control (historical vs. future access)
- ⚠️ Revoked member retains access to old content (unless re-encrypted)

**For high-security scenarios:**
- Re-encrypt all objects with new key (computationally expensive)
- Use time-limited keys (automatic rotation)

---

## Integration with Cloud Storage

### Cloud Storage as "Git Remote"

**Architecture:**

```
Client (Genesis-Tool):
├─ Git-like object database (local)
├─ Encryption/decryption engine
├─ Conflict detection
└─ AI merge engine

Cloud Storage (e.g., encrypted drive):
├─ Stores encrypted objects
├─ Provides sync/download
├─ No access to content
└─ Acts as "dumb" remote storage
```

**Workflow:**

```
1. User creates/edits content
   └─ Encrypted locally, stored as objects

2. User pushes to cloud
   └─ Uploads encrypted objects

3. Other team members pull
   └─ Downloads encrypted objects

4. Conflict detected
   └─ Client-side merge (AI-assisted)

5. Merge commit pushed
   └─ All team members sync
```

---

## Performance Considerations

### Differential Sync

**Challenge:** Syncing thousands of objects is slow.

**Solution:**
- Only sync changed objects (like Git)
- Use content-addressable storage (hash-based)
- Implement efficient pack files (bundle related objects)

### Caching Layer

**Challenge:** Decrypting large object graphs is expensive.

**Solution:**
- Cache decrypted objects in memory (encrypted at rest)
- Lazy loading (decrypt on demand)
- Background pre-fetching (predict needed objects)

---

## Comparison: Traditional vs. Git-Like

| Aspect | Traditional File Sync | Git-Like Object Storage |
|--------|----------------------|-------------------------|
| **Conflict Handling** | Creates duplicate files | Detects and merges |
| **Granularity** | Entire file | Individual objects |
| **Zero-Access** | ❌ Breaks on conflict | ✅ Maintained |
| **Merge Strategy** | Manual copy-paste | AI-assisted semantic |
| **Audit Trail** | None | Cryptographic signatures |
| **Performance** | Fast (simple sync) | Slower (object graph) |

---

## Security Considerations

### Threat Model

**Protected Against:**
- ✅ Server compromise (server never sees content)
- ✅ Man-in-the-middle (end-to-end encryption)
- ✅ Unauthorized access (key-based authentication)
- ✅ Tampering (cryptographic signatures)

**Not Protected Against:**
- ⚠️ Client compromise (malware on user's device)
- ⚠️ Weak passwords (user responsibility)
- ⚠️ Social engineering (user must verify identities)

### Best Practices

1. **Strong Passwords:** Use password manager
2. **Key Verification:** Verify public keys out-of-band
3. **Regular Rotation:** Rotate team keys periodically
4. **Audit Logs:** Review signed commits regularly
5. **Backup Keys:** Secure backup of private keys

---

## Conclusion

Zero-Access Collaboration solves the fundamental conflict between encryption and teamwork. By combining Git-like architecture with AI-powered semantic merging, it enables real-time collaboration without compromising sovereignty.

**Key Achievements:**
- ✅ **Zero-Access Maintained:** Server never sees content
- ✅ **Conflict Resolution:** AI understands meaning, not just text
- ✅ **Cryptographic Audit:** Every change is signed and verifiable
- ✅ **Scalable Architecture:** From 2-person teams to enterprises
- ✅ **Privacy-First:** User controls keys, data, and sharing

**This is collaborative sovereignty.**

---

## Learn More

- **[Collaborative Workspaces](collaborative-workspaces.md)** – High-level collaboration features
- **[Blockchain for Thoughts](../06-future/blockchain-for-thoughts.md)** – Cryptographic proof of authorship
- **[Architecture Overview](../01-architecture/overview.md)** – The 3-layer architecture

---

**From isolated sovereignty to collaborative sovereignty.**


