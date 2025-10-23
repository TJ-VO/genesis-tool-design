# Genesis-Tool Architecture

---

## Overview

Genesis-Tool's architecture is built on **3 hierarchical layers**, each serving a distinct purpose in the knowledge creation and management workflow.

**Core Insight:** Knowledge work requires different spaces for different activities. Creating knowledge (Genesis Deck) needs different workflows than storing it (Sanctuary) or sharing it (Community).

---

## The 3-Layer Architecture

```
┌──────────────────────────────────────────────────────────┐
│                      GENESIS TOOL                        │
├──────────────────────────────────────────────────────────┤
│                                                          │
│                  🏛️ SANCTUARY                            │
│              (Your Private Knowledge)                    │
│                        │                                 │
│                        ↓                                 │
│          ┌─────────────────────────────┐                 │
│          │        GENESIS DECK         │                 │
│          │     🔍  ↔  🌟  ↔  🔄        │                 │
│          │ Research Create Refine      │                 │
│          └─────────────────────────────┘                 │
│                        ↓                                 │
│                        │                                 │
│                  💬 COMMUNITY                            │
│              (Global Knowledge Network)                  │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

**Keyboard Shortcuts:**
- `Ctrl+1`: Sanctuary
- `Ctrl+2`: Genesis Deck → Research Mode
- `Ctrl+3`: Genesis Deck → Create Mode (default)
- `Ctrl+4`: Genesis Deck → Refine Mode
- `Ctrl+5`: Community Deck

---

## Architectural Hierarchy

### **Layer 1: Sanctuary (Top)**
**Purpose:** Where knowledge LIVES  
**Nature:** Persistent, private, user-curated  
**Metaphor:** Temple, treasury, archive

**Key Characteristics:**
- Long-term knowledge storage
- User-organized structure (folders, tags)
- Grows over months and years
- Compounding value (knowledge builds on knowledge)

**Learn more:** [../02-sanctuary/overview.md](../02-sanctuary/overview.md)

---

### **Layer 2: Genesis Deck (Middle)**
**Purpose:** Where knowledge is CREATED  
**Nature:** Temporary, process-oriented, AI-assisted  
**Metaphor:** Workshop, laboratory, studio

**The Name "Genesis":**
> **Genesis** (Greek: γένεσις) = "origin, creation, beginning"
> 
> The Genesis Deck is where knowledge is **born**—hence the name of the tool itself.

**Key Characteristics:**
- Session-based workspaces (not persistent)
- 3 specialized modes for different cognitive tasks
- Loads context FROM Sanctuary
- Saves curated results TO Sanctuary

**The 3 Modes:**

#### 🔍 **Research Mode**
**Purpose:** Gather facts, sources, and evidence  
**Cognitive Mode:** Systematic, evidence-based, source-critical  
**Output:** Dossiers, source collections, AI analysis

#### 🌟 **Create Mode**
**Purpose:** Generate knowledge through conversation and exploration  
**Cognitive Mode:** Divergent, exploratory, reflective  
**Output:** Summaries, Q&A pairs, insights, drafts

#### 🔄 **Refine Mode**
**Purpose:** Iteratively improve documents with multi-agent feedback  
**Cognitive Mode:** Convergent, critical, iterative  
**Output:** Polished, final-version documents

**Learn more:** [../03-genesis-deck/overview.md](../03-genesis-deck/overview.md)

---

### **Layer 3: Community Deck (Bottom)**
**Purpose:** Where knowledge is SHARED  
**Nature:** Global, collaborative, curated  
**Metaphor:** Agora, marketplace of ideas, public square

**Key Characteristics:**
- Global knowledge network
- Thematic chat rooms (connect by interests)
- Global Wiki (collaborative knowledge base)
- Multi-layer privacy filter (safe publishing)

**Learn more:** [../04-community/overview.md](../04-community/overview.md)

---

## Knowledge Flow: The Two Axes

### **Vertical Axis: Depth (Sanctuary ↔ Genesis Deck ↔ Community)**

```
🏛️ SANCTUARY (Private, Persistent)
    ↕ Load & Save
🌟 GENESIS DECK (Temporary, Workspaces)
    ↕ Import & Publish
💬 COMMUNITY (Global, Collaborative)
```

**Flow Examples:**
1. **Sanctuary → Genesis Deck:** Load existing knowledge as context for new work
2. **Genesis Deck → Sanctuary:** Save curated results for long-term storage
3. **Community → Genesis Deck:** Import global knowledge for local use
4. **Genesis Deck → Community:** Publish curated knowledge (after privacy filter)

---

### **Horizontal Axis: Workflow (Research ↔ Create ↔ Refine)**

```
🔍 Research ↔ 🎨 Create ↔ 🔄 Refine
(Within Genesis Deck)
```

**Flow Examples:**
1. **Research → Create:** Gather facts, then write
2. **Create → Research:** Have idea, then find evidence
3. **Create → Refine:** Draft document, then polish
4. **Refine → Create:** Get feedback, then rewrite

**Key Insight:** Users can move freely between modes within a single session. The Genesis Deck is ONE workspace with 3 modes, not 3 separate workspaces.

---

## Why This Architecture?

### **Problem with Traditional Tools:**

**One-Size-Fits-All Interfaces:**
```
Traditional AI Chat Tools:
- Same linear chat for all tasks
- No persistence (sessions disappear)
- No structure (everything is a chat)
- No specialization (exploration = research = refinement)
```

**File-System Based Tools:**
```
- File-based (monolithic, not granular)
- Manual organization (AI can't help)
- No conversation-native design
```

**Document-Centric Platforms:**
```
- Page-based (not conversation-first)
- No branching concept
- AI is bolt-on, not core
```

---

### **Genesis-Tool Solution:**

**3-Layer Hierarchy:**
- **Sanctuary:** Solves persistence problem (knowledge doesn't disappear)
- **Genesis Deck:** Solves specialization problem (different modes for different tasks)
- **Community:** Solves isolation problem (knowledge can be shared safely)

**2-Axis Workflow:**
- **Vertical:** Solves depth problem (private ↔ workspace ↔ global)
- **Horizontal:** Solves process problem (gather ↔ create ↔ refine)

---

## Real-World Example: Research Workflow

### **Phase 1: Research Mode (Genesis Deck)**
```
Topic: "Urban heat island mitigation strategies"
→ AI finds primary studies (Smith et al. 2023, Nature Climate Change)
→ AI finds meta-analyses (IPCC AR6 Working Group II)
→ AI finds theoretical frameworks (Resilience Theory)
→ Save to Sanctuary: "Research → Climate → Urban Adaptation"
```

### **Phase 2: Create Mode (Genesis Deck)**
```
Load context: Research framework from Sanctuary
→ Discuss: "What are the most effective strategies?"
→ Branch 1: Explore green infrastructure approaches
→ Branch 2: Explore policy interventions
→ Save summaries to Sanctuary
```

### **Phase 3: Refine Mode (Genesis Deck)**
```
Load context: Research framework + strategy summaries
→ Content AI drafts literature review
→ Critic AI critiques methodology and gaps
→ Strategy AI optimizes structure and argumentation
→ Save final manuscript to Sanctuary
```

### **Phase 4: Create Mode (Genesis Deck)**
```
Load context: Final manuscript + research framework
→ Discuss: "What are the research gaps?"
→ Branch: Explore future research directions
→ Save research proposal to Sanctuary
```

**Result:**
- **Sanctuary:** Reusable research framework, final manuscript, research proposals
- **Genesis Deck:** All research and discussion preserved (can revisit)
- **Community:** (Optional) Publish literature review for other researchers

---

## Design Principles

### **1. Separation of Concerns**
- **Sanctuary:** Storage (what to keep)
- **Genesis Deck:** Creation (how to work)
- **Community:** Sharing (what to publish)

### **2. User Control**
- **No auto-summarization** (user chooses what to save)
- **No auto-publishing** (user controls privacy)
- **No auto-organization** (user curates structure)

### **3. AI as Partner, Not Master**
- AI suggests, user decides
- AI structures, user curates
- AI generates, user refines

### **4. Privacy by Design**
- Sanctuary is always local and encrypted
- Community publishing requires explicit user action
- Multi-layer privacy filter before any data leaves

---

---

## Learn More

- **Overall Architecture:** This document
- **Sanctuary (Where knowledge is stored):** [../02-sanctuary/overview.md](../02-sanctuary/overview.md)
- **Genesis Deck (Where knowledge is created):** [../03-genesis-deck/overview.md](../03-genesis-deck/overview.md)
- **Community Deck (Where knowledge is shared):** [../04-community/overview.md](../04-community/overview.md)
- **Competitive Differentiation:** [../../competitive-differentiation.md](../../competitive-differentiation.md)

---

## Design Decision Record

**Why "Genesis Deck" instead of "Process Deck" or "Creation Deck"?**

1. **Explains the tool name:** "Genesis" = creation, origin → Genesis Deck is where knowledge is born
2. **Poetic and memorable:** More inspiring than "Process Deck"
3. **Distinctive:** Establishes clear identity and purpose
4. **Philosophically aligned:** Fits with "Sanctuary" (spiritual, valuable)

**Why 3 layers instead of 5 separate decks?**

1. **Reflects actual workflow:** Users don't switch between 5 equal areas, they work in Genesis Deck and save to Sanctuary
2. **Clearer hierarchy:** Sanctuary is the hub, Genesis Deck is the workspace, Community is the network
3. **Reduces cognitive load:** 3 layers is simpler than 5 equal areas
4. **Enables fluid workflow:** Users can switch between Research/Create/Refine modes without leaving Genesis Deck

**Why horizontal workflow (Research ↔ Create ↔ Refine)?**

1. **No forced sequence:** Users can start with any mode (Create → Research or Research → Create)
2. **Create is central:** Most common mode, positioned in the middle
3. **Reflects reality:** Knowledge work is iterative, not linear

---

## Core Features and Technologies

This section provides a detailed overview of Genesis-Tool's core technical features and their benefits.

### 1. Zero-Access Encryption

Your conversations are encrypted with YOUR password using industry-standard cryptography (PBKDF2 + Fernet).  
The architecture is designed to prevent server operator access to plaintext data.

**Key benefit:** Privacy-first architecture with client-side key derivation. See [DISCLAIMER.md](../../DISCLAIMER.md) for security limitations and user responsibilities.

### 2. Automatic Branching ("Chat-Multiverse")

Edit any past message with `@edit <position> <text>` → Genesis automatically creates a parallel timeline.
Explore "what if" scenarios without losing the original conversation, or create new, focused branches that carry only the relevant context forward. This is powered by block-filtered branching, allowing you to distill a single topic from a complex discussion.

**Auto-Branching Triggers:**
- **On Edit (always):** `@edit 3 Tell me about dogs` → Creates branch "main-edit-msg3"
- **On Summary (optional, configurable):** `@sum` → Can create new branch or stay in same chat (user-configurable via `@settings`)
  - **With branching:** Choose context window (0 to N Q&A pairs) → Creates focused summary branch
  - **Without branching:** Summary added to current chat, all messages kept (non-destructive)

**Key benefit:** Fearless editing—history is always preserved, alternatives are always explorable.

### 3. Cross-Session Topic Search

Search: "JWT authentication" → Find ALL relevant message-pairs across months of conversations.  
Aggregate results into a new focused branch.

**Key benefit:** Your knowledge persists indefinitely with semantic connections across time.

### 4. Smart Summarization & Knowledge Integration

AI-generated summaries aren't just for compressing context; they are automatically saved as persistent items in your **Sanctuary** (persistent knowledge storage). Any summary can then be loaded as context into a completely different conversation, creating a continuous loop of knowledge refinement and reuse.

**Context Window Control:** When creating summary branches, choose how many Q&A pairs to keep (0 to N). This enables:
- **Focused summaries:** Keep only last 2 pairs for clean slate
- **Full context:** Keep all pairs for complete history
- **Hierarchical compression:** AI sees old summaries (iterative refinement)

**Transclusion Philosophy:** Summaries are not automatically copied to new branches. Instead, users manually load them via the Sanctuary (future UI: drag-drop "Context as Lego Blocks").

**Key benefit:** Transforms messy conversations into clean, reusable knowledge assets that compound in value over time.

### 5. Visual Knowledge Navigation

Conversations organized as semantic mindmaps (thematic blocks).  
See relationships, not just chronological lists.

**Key benefit:** A structured knowledge graph for precise navigation—no more endless scrolling.

### 6. Document Versioning

Full version history tracking for all documents with automatic versioning.  
Every change creates a new version while preserving the complete history.

**Key features:**
- **Automatic versioning:** Every document update creates a new version
- **Version history:** Access any previous version at any time
- **Non-destructive:** Original versions are never deleted
- **Rollback support:** Restore any previous version if needed

**Key benefit:** Never lose work, track changes over time, experiment fearlessly.

### 7. User-Friendly Configuration

Unified `@settings` menu for all configuration:
- **AI Model & Privacy:** Choose between cloud providers (e.g., Gemini, Claude, GPT) or local AI (e.g., Ollama) in one menu
- **Summary Behavior:** Configure whether summaries create new branches or stay in same chat
- **Advanced Settings:** Customize prompts, tags, and topics for your workflow

**Note:** Provider names (Gemini, Claude, GPT, Ollama) are mentioned for technical reference only and do not constitute endorsement, comparison, or affiliation. All trademarks remain the property of their respective owners. See [DISCLAIMER.md](../../DISCLAIMER.md) for trademark information.

**Key benefit:** Simple, intuitive configuration without technical complexity—privacy and automation settings in one place.

---


