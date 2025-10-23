# Features Directory

This directory contains detailed **feature specifications** and **UI/UX designs** for Genesis-Tool. These are concrete designs for features to be implemented in the frontend.

---

## Directory Structure

We use a **hierarchical folder structure** organized by the 3-layer architecture and user journey. This ensures:
- ✅ **Clear Navigation:** Follow the numbered folders (01 → 08) for the complete story
- ✅ **Logical Grouping:** Related concepts are together in folders
- ✅ **Scalability:** Easy to add new concepts within existing categories
- ✅ **Maintainability:** No prefix confusion, folder names are self-explanatory

---

## 📂 Folder Overview

```
features/
├── 01-architecture/          # Fundamental architectural principles
├── 02-sanctuary/             # Layer 1: Persistent Knowledge
├── 03-genesis-deck/          # Layer 2: Knowledge Creation (3 modes)
│   ├── create-mode/          # Exploratory thinking features
│   ├── refine-mode/          # Document refinement features
│   └── research-mode/        # Systematic research features (planned)
├── 04-community/             # Layer 3: Global Knowledge Network
├── 05-workflows/             # Workflow patterns and systems
├── 06-future/                # Future vision features
├── 07-validation/            # Real-world use cases & validation
```

---

## 🎯 User Journey (Recommended Reading Order)

### **Start Here: Understanding the Foundation**

**01. Architecture** - Learn the core concepts
- [`overview.md`](01-architecture/overview.md) - The 3-layer architecture (Sanctuary, Genesis Deck, Community)
- [`separation-of-concerns.md`](01-architecture/separation-of-concerns.md) - Context isolation principle
- [`history-editing.md`](01-architecture/history-editing.md) - Git-like history editing (non-destructive principle)

---

### **Layer 1: Sanctuary (Your Knowledge Treasury)**

**02. Sanctuary** - Where knowledge is stored
- [`overview.md`](02-sanctuary/overview.md) - Persistent, private knowledge storage
- [`visual-mindmap.md`](02-sanctuary/visual-mindmap.md) - Hierarchical knowledge visualization
- [`transclusion.md`](02-sanctuary/transclusion.md) - "Context as Lego Blocks" concept

---

### **Layer 2: Genesis Deck (Where Knowledge is Created)**

**03. Genesis Deck** - The central workspace with 3 modes
- [`overview.md`](03-genesis-deck/overview.md) - The 3 modes explained (Research, Create, Refine)

**03a. Create Mode** 🌟 - Exploratory thinking
- [`message-navigation.md`](03-genesis-deck/create-mode/message-navigation.md) - VSCode-style minimap
- [`visual-branch-differentiation.md`](03-genesis-deck/create-mode/visual-branch-differentiation.md) - Branch type visualization

**03b. Refine Mode** 🔄 - Document refinement
- [`cascading-critique.md`](03-genesis-deck/refine-mode/cascading-critique.md) - Multi-level document review
- [`multi-agent-canvas.md`](03-genesis-deck/refine-mode/multi-agent-canvas.md) - Visual workflow orchestration

**03c. Research Mode** 🔍 - Systematic research
- [`PLACEHOLDER.md`](03-genesis-deck/research-mode/PLACEHOLDER.md) - Placeholder for future design

---

### **Layer 3: Community (Global Knowledge Network)**

**04. Community** - Where knowledge is shared
- [`overview.md`](04-community/overview.md) - Thematic chat rooms, Global Wiki, collaboration
- [`collaborative-workspaces.md`](04-community/collaborative-workspaces.md) - Multi-user collaboration

---

### **Cross-Cutting Concepts**

**05. Workflows** - Patterns that span multiple layers
- [`parallel-query-branching.md`](05-workflows/parallel-query-branching.md) - Fork-Query-Merge pattern
- [`multi-scenario-epistemic-roleplay.md`](05-workflows/multi-scenario-epistemic-roleplay.md) - Multi-scenario simulation
- [`template-system.md`](05-workflows/template-system.md) - Predefined multi-agent workflows
- [`ai-tool-orchestration.md`](05-workflows/ai-tool-orchestration.md) - AI-guided workflows

**06. Future** - Long-term vision features
- [`blockchain-for-thoughts.md`](06-future/blockchain-for-thoughts.md) - Anonymous publishing with cryptographic proof
- [`collaborative-knowledge-network.md`](06-future/collaborative-knowledge-network.md) - "GitHub for Knowledge"
- [`education-use-case.md`](06-future/education-use-case.md) - Lifelong learning companion
- [`productivity-integrations.md`](06-future/productivity-integrations.md) - Calendar, email, task management

**07. Validation** - Real-world proof
- [`real-world-use-cases.md`](07-validation/real-world-use-cases.md) - Anonymized real-world examples

---

## 📊 Feature Scope Overview

### **Core Features**
- Session branching (Create Mode)
- Thematic blocks (Create Mode)
- Sanctuary/Inventory system
- Zero-access encryption
- Multi-provider AI support

### **Visual Interface Features**
- Visual mindmap (Sanctuary)
- Message navigation minimap (Create Mode)
- Branch visualization (Create Mode)

### **Advanced Workflows**
- Research Mode (systematic fact gathering)
- Refine Mode (multi-agent workflows)
- Community Deck (global knowledge network)
- Advanced workflows (parallel branching, multi-scenario)

### **Future Vision Features**
- Blockchain for Ideas
- Collaborative Knowledge Network
- Education features
- Productivity integrations

---

## 🎨 Design Philosophy

### Convention Over Configuration
- Smart defaults for common cases
- Explicit control for advanced users
- Progressive disclosure (beginners → advanced)

### Non-Destructive Operations
- History always preserved
- Branching creates safety net
- Full version tracking

### Privacy by Design
- Zero-access encryption
- Local-first architecture
- Self-hosting option
- User sovereignty

### User Control First
- No auto-summarization (user chooses)
- No auto-publishing (user controls privacy)
- No auto-organization (user curates)

---

## 🔗 Learn More

- **Main Documentation:** [../README.md](../README.md)
- **Design Philosophy:** [../design-philosophy.md](../design-philosophy.md)

---

## 📝 Contributing

Want to add a new concept document?

1. **Determine the category:**
   - Architecture principle? → `01-architecture/`
   - Sanctuary feature? → `02-sanctuary/`
   - Create Mode feature? → `03-genesis-deck/create-mode/`
   - Refine Mode feature? → `03-genesis-deck/refine-mode/`
   - Research Mode feature? → `03-genesis-deck/research-mode/`
   - Community feature? → `04-community/`
   - Workflow pattern? → `05-workflows/`
   - Future vision? → `06-future/`
   - Use case validation? → `07-validation/`

2. **Create the file** with a descriptive name (no prefixes needed!)

3. **Update this README** in the appropriate section

4. **Follow the template** from existing documents

---

