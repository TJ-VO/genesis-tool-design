# Context Control Through Transclusion

## The Problem with Traditional AI Chat

Current AI chat tools force users into linear, monolithic contexts:
- All messages in one session = one unchangeable context
- No way to combine insights from multiple conversations
- Context grows uncontrollably, hitting token limits
- Knowledge is trapped in individual sessions

**Result:** Users manually copy-paste between sessions, repeat context, or lose valuable insights.

## Genesis-Tool's Solution: Context as Lego Blocks

### Core Concept

**Transclusion** = Build AI context by combining knowledge artifacts from multiple sources, like assembling Lego blocks.

Users compose context from:
- **Summaries** (compressed conversation history)
- **Topic Blocks** (thematic segments, auto-extracted)
- **Documents** (uploaded files)
- **Message Pairs** (specific Q&A exchanges)

### Visual Example

```
Research Project: "Implement Secure Authentication"

Context Built From:
┌─────────────────────────────────────────┐
│ Summary: OAuth Basics (Session A)       │
│ Block: JWT Implementation (Session B)   │
│ Block: Security Best Practices (C)      │
│ Document: OWASP Auth Cheatsheet         │
│ Last 2 Q&A pairs (current session)      │
└─────────────────────────────────────────┘
         ↓
    AI sees complete, curated context
    without loading 50+ sessions
```

## Use Cases

### 1. Research Workflow
**Problem:** Knowledge scattered across multiple sessions
**Solution:** Combine summaries and blocks into one focused session

**Example:**
- Week 1: Explore authentication (10 sessions)
- Week 2: Create summaries (compress knowledge)
- Week 3: Load relevant summaries into new session
- **Result:** AI has complete context, no redundancy

### 2. Cross-Project Knowledge Transfer
**Problem:** Need insights from multiple projects
**Solution:** Transclude artifacts from different sessions

**Example:**
```
New Session: "Integrate payment gateway into e-commerce"
Load:
  - Summary: "E-commerce Architecture" (Project A)
  - Summary: "Payment Gateway API" (Project B)
  - Block: "Database Schema" (Project A)
  - Document: Integration Spec
```

### 3. Iterative Knowledge Refinement
**Problem:** Context becomes bloated over time
**Solution:** Hierarchical compression through summaries

**Example:**
- Session 1-10: Raw conversations (100 messages)
- Summary A: Compress to 1 summary (10 paragraphs)
- Session 11-20: More conversations + Summary A
- Summary B: Compress everything (5 paragraphs)
- **Result:** 200 messages → 5 paragraphs, no information loss

## Competitive Advantage

| Feature              | Traditional AI Chat     | Genesis-Tool               |
|----------------------|-------------------------|----------------------------|
| **Context Building** | Linear (all or nothing) | Compositional (Lego blocks)|
| **Knowledge Reuse**  | Manual copy-paste       | Transclusion (reference)   |
| **Cross-Session**    | Not possible            | Native support             |
| **Token Efficiency** | Uncontrolled growth     | User-curated context       |
| **Control**          | Automatic (no choice)   | Explicit (full control)    |

## Why This Matters

### For Individual Users
- **Efficiency:** Reuse knowledge without repetition
- **Control:** Decide exactly what AI sees
- **Scalability:** Manage large projects without context bloat
- **Quality:** Iteratively refine and compress knowledge

### For Teams
- **Collaboration:** Share summaries and blocks
- **Onboarding:** Load curated context for new members
- **Standards:** Context templates for common tasks
- **Knowledge Base:** Build organizational memory

### For Enterprises
- **Compliance:** Control what data AI accesses
- **Efficiency:** Reduce redundant context (cost savings)
- **Quality:** Curated knowledge = better AI responses
- **Scalability:** Manage thousands of sessions

## Design Evolution

### Foundation: Core Inventory System
- Inventory system (summaries, blocks, documents)
- `@inv load` to add artifacts to session
- Summary context window (last N pairs)
- Auto-branching (preserve history)

### Enhanced CLI Capabilities
- Multiple item loading (`@inv load summary-1 block-2 doc-3`)
- Context visibility (`@context show`)
- Hierarchical summaries (summary includes old summaries)

### Visual Interface
- Mindmap-style session visualization
- Drag-drop artifacts into sessions
- Visual context builder
- Context presets and templates

## Design Philosophy

### Convention Over Configuration
- Smart defaults for common cases
- Explicit control for advanced users
- No complex UI for basic operations

### Non-Destructive Operations
- Transclusion = reference, not copy
- Original artifacts never modified
- Full history always preserved

### Progressive Disclosure
- **Beginners:** Linear chat (just works)
- **Intermediate:** Summaries, branches
- **Advanced:** Transclusion, full control

## Technical Foundation

**Transclusion is enabled by:**
1. **Message Type System** (ADR-013)
   - Distinct types: `chat`, `document_ref`, `summary`, `block`
   - Clear semantics for each type

2. **Sanctuary** (ADR-006, also known as "Inventory" in backend code)
   - Central storage for all artifacts
   - Metadata, tags, relationships

3. **Context Window Management** (ADR-012)
   - User controls what gets copied to new branches
   - Explicit vs. implicit context

4. **Non-Destructive Principle** (ADR-015)
   - Operations preserve original data
   - Branching creates safety net

## Future Vision

### AI-Assisted Context Building
- **Smart suggestions:** "These 3 summaries are relevant"
- **Auto-composition:** "I've loaded relevant blocks"
- **Optimization:** "Remove these to save tokens"

### Collaborative Knowledge
- **Shared artifacts:** Team knowledge base
- **Context templates:** Reusable patterns
- **Marketplace:** Community-curated contexts

### Cross-Session Intelligence
- **Semantic search:** Find all discussions about X
- **Topic clustering:** Group sessions by theme
- **Knowledge gaps:** Identify missing information

## Why Now?

**Market Timing:**
1. **Branching is mainstream** (validated by major platforms, 2025)
2. **Token costs matter** (efficiency = competitive advantage)
3. **Enterprise adoption** (control and compliance requirements)
4. **Power users emerge** (demand advanced features)

**Genesis-Tool Position:**
- Extends mainstream branching with transclusion
- Solves real pain point (context management)
- Distinctive approach to context composition
- Privacy-first architecture enables it (zero-access = user control)

## For Developers

**Transclusion is not just a feature—it's an architecture:**
- Enables knowledge graphs (sessions as nodes, artifacts as edges)
- Supports semantic search (find relevant context)
- Allows AI-assisted curation (suggest context)
- Scales to enterprise (thousands of sessions)

**Implementation architecture:**
- Comprehensive REST API design
- Extensive test coverage
- PostgreSQL-ready schema
- Zero-access encryption throughout

## Summary

**Genesis-Tool transforms AI chat from linear conversations into a knowledge graph.**

Users don't just chat—they build, refine, and compose knowledge. Context becomes a first-class citizen, not an afterthought.

**"Context as Lego Blocks"** is the future of AI-assisted knowledge work.

