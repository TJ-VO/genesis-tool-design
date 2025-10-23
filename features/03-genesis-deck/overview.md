# Genesis Deck - Where Knowledge is Created

---

## Overview

The **Genesis Deck** is where knowledge is **created**. It's the central workspace of Genesis-Tool, featuring 3 specialized modes for different cognitive tasks: Research, Create, and Refine.

**The Name "Genesis":**
> **Genesis** (Greek: γένεσις) = "origin, creation, beginning"
> 
> The Genesis Deck is where knowledge is **born**—hence the name of the tool itself.

---

## Core Characteristics

### **1. Temporary**
- Session-based workspaces (not persistent like Sanctuary)
- Active while you're working
- Archived when session ends

### **2. Process-Oriented**
- Optimized for creation, not storage
- Flexible workflow (Research ↔ Create ↔ Refine)
- Seamless mode switching

### **3. AI-Assisted**
- AI as partner, not master
- Context-aware (loads from Sanctuary)
- Multi-agent support (Refine Mode)

### **4. Feeds Sanctuary**
- All curated results save to Sanctuary
- User decides what to keep
- No auto-summarization

---

## The 3 Modes

```
🔍 Research ↔ 🎨 Create ↔ 🔄 Refine
```

**Key Insight:** These are not 3 separate workspaces—they are 3 modes within ONE workspace. Users can switch freely between them within a single session.

---

## 🔍 Research Mode - Systematic Fact Gathering

**Purpose:** Deep-dive research on ONE topic with source tracking and AI analysis

**Cognitive Mode:** Systematic, evidence-based, source-critical  
**Mental Model:** "I need to understand this topic deeply"

---

### The Distinction from Sanctuary

**Research Mode = "The Workshop" 🔬**
- **Session-based:** Temporary, focused on ONE topic
- **AI-generated structure:** Automatically organized by source type
- **Raw materials:** Research results + AI analysis
- **Lifespan:** Active session, then archived
- **Metaphor:** Workshop, laboratory, workplace
- **Purpose:** "I'm building knowledge about THIS topic"

**Sanctuary = "The Treasury" 🏛️**
- **Persistent:** Grows over months and years
- **User-curated structure:** Organized by YOUR mental model
- **Refined knowledge:** Summaries + selected Q&A
- **Lifespan:** Long-term knowledge storage
- **Metaphor:** Library, archive, treasure vault
- **Purpose:** "This is MY knowledge base—it grows with every session"

**The Workflow:**
```
Research Mode (Session: "Urban heat island mitigation strategies")
    ↓
Work with AI to analyze sources and build understanding
    ↓
Condense to Summary + selected Q&A pairs
    ↓
Save to Sanctuary
(User chooses: Research → Climate → Urban Adaptation)
    ↓
Research session archived (can revisit if needed)
```

---

### Key Features

**Multi-Source Search (Planned):**
- Web search (privacy-focused search engines, academic databases)
- Document search (PDFs, local files)
- Sanctuary search (your existing knowledge)
- API integrations (legal databases, scientific journals)

**AI-Powered Analysis (Planned):**
- Automatic source categorization (primary study, meta-analysis, review)
- Relevance scoring (tiered: highly relevant → marginally relevant)
- Citation extraction (automatic footnotes)
- Contradiction detection (AI flags conflicting sources)

**Serendipity Reservoir (Planned):**
- Quick capture for off-topic insights
- Doesn't break focus (deferred processing)
- Review later: "Save to Sanctuary" or "Discard"

**Timeline View (Planned):**
- Chronological view of research progress
- See when sources were added
- Track AI analysis iterations

---

### UI Layout (Planned)

```
┌────────────────────────────────────────────────────────────┐
│ 🔍 RESEARCH MODE                                           │
├────────────────────────────────────────────────────────────┤
│                                                            │
│  ┌─────────────┬────────────────────────────────────────┐  │
│  │             │                                        │  │
│  │  LEFT       │          RIGHT                         │  │
│  │  PANEL      │          PANEL                         │  │
│  │             │                                        │  │
│  │ Source Tree │  Preview + Timeline                    │  │
│  │ (Tiered)    │                                        │  │
│  │             │  [Source Preview]                      │  │
│  │ 📚 Primary  │  Smith et al. 2023: Urban Heat Islands │  │
│  │ ├─ Smith 23 │  "Green infrastructure reduces..."     │  │
│  │ └─ Chen 22  │                                        │  │
│  │             │  [AI Analysis]                         │  │
│  │ 📊 Meta     │  Key Points: ...                       │  │
│  │ ├─ IPCC AR6 │                                        │  │
│  │ └─ Review 23│  [Timeline]                            │  │
│  │             │  10:00 - Added Smith et al.            │  │
│  │ 📖 Theory   │  10:15 - AI analyzed                   │  │
│  │ └─ Holling  │  10:30 - Added meta-analysis           │  │
│  │             │                                        │  │
│  └─────────────┴────────────────────────────────────────┘  │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

---

### When to Use

- **Academic Research:** Gather papers, citations, evidence
- **Technical Research:** API docs, Stack Overflow, GitHub issues
- **Market Research:** Competitor analysis, industry reports
- **Scientific Research:** Primary studies, meta-analyses, theoretical frameworks
- **Product Research:** User studies, feature analysis, competitive analysis

---

### Real-World Example

```
Topic: "Urban heat island mitigation strategies"

1. User starts Research Mode
2. AI searches:
   - Primary Studies: Smith et al. 2023, Chen & Wang 2022
   - Meta-Analyses: IPCC AR6 Working Group II, Systematic Review 2023
   - Theoretical Frameworks: Holling 1973, Walker et al. 2004
3. AI categorizes sources (Primary Study, Meta-Analysis, Theory)
4. User analyzes with AI assistance:
   - "Summarize Smith et al. key findings"
   - "Compare green infrastructure vs. cool pavements"
   - "What are the cost-benefit trade-offs?"
5. Off-topic idea? → Quick add to Serendipity Reservoir
6. Session complete → Export summary + selected Q&A to Sanctuary
   (User chooses: Research → Climate → Urban Adaptation)
```

**Output:** Structured dossier with 15 relevant studies, 3 meta-analyses, 2 theoretical frameworks—all cited and analyzed.

---

### Status

**Planned for Future**

**Backend Support:** Session branching, AI analysis, document management (already implemented)  
**Frontend Needed:** Source tree UI, Serendipity Reservoir, citation export

---

## 🌟 Create Mode - Exploratory Thinking

**Purpose:** Generate knowledge through conversation and exploration

**Cognitive Mode:** Divergent, exploratory, reflective  
**Mental Model:** "I want to think through different perspectives"

---

### Key Features

**Session Branching (Implemented):**
- Automatic branching on edit (Edit-Safety)
- Manual branching for "what-if" scenarios
- Parallel exploration (multiple branches simultaneously)

**Mindmap Visualization (Planned):**
- Visual session tree (see all branches at once)
- Click to navigate between branches
- Color-coding by topic or status

**Thematic Blocks (Implemented):**
- AI-powered conversation segmentation
- Automatic topic extraction
- Navigate by theme (not just chronology)

**Message History with Minimap (Planned):**
- VSCode-style minimap for long conversations
- Instant navigation (click to jump)
- Visual overview of conversation structure

**Context Control (Implemented):**
- Load knowledge from Sanctuary
- Load multiple items at once (compose context)
- Preview before loading

---

### UI Layout (Planned)

```
┌──────────────────────────────────────────────────────┐
│ 🌟 CREATE MODE                                       │
├──────────────────────────────────────────────────────┤
│                                                      │
│  ┌─────────────┬──────────────────────────────────┐  │
│  │             │                                  │  │
│  │  LEFT       │          RIGHT                   │  │
│  │  PANEL      │          PANEL                   │  │
│  │             │                                  │  │
│  │ Mindmap     │  Messages + Minimap              │  │
│  │ (Session    │                                  │  │
│  │  Tree)      │  User: Should I use TypeScript?  │  │
│  │             │  AI: Let's explore pros/cons...  │  │
│  │ ● Main      │                                  │  │
│  │ ├─ Branch A │  User: What about performance?   │  │
│  │ │  (TS Pros)│  AI: TypeScript adds...          │  │
│  │ └─ Branch B │                                  │  │
│  │    (TS Cons)│  [Minimap]                       │  │
│  │             │  ████ Current view               │  │
│  │             │  ░░░░ Earlier messages           │  │
│  │             │  ░░░░ Later messages             │  │
│  │             │                                  │  │
│  └─────────────┴──────────────────────────────────┘  │
│                                                      │
└──────────────────────────────────────────────────────┘
```

---

### When to Use

- **Exploring Ideas:** Brainstorm different solutions to a problem
- **Understanding Topics:** Q&A to build mental models
- **Decision Making:** Explore pros/cons of different options
- **Writing Drafts:** Generate initial content for refinement
- **Strategic Planning:** Think through scenarios and contingencies

---

### Real-World Example

```
Topic: "Should I migrate to TypeScript?"

1. User starts Create Mode
2. Load context from Sanctuary: "JavaScript Best Practices"
3. Conversation:
   User: "Should I migrate to TypeScript?"
   AI: "Let's explore pros and cons..."
   
4. Branch A: "TypeScript Pros"
   - Type safety
   - Better IDE support
   - Easier refactoring
   
5. Branch B: "TypeScript Cons"
   - Learning curve
   - Build complexity
   - Migration effort
   
6. User compares branches
7. Decision: "Yes, migrate"
8. Save summary to Sanctuary: "Technology → Backend → TypeScript"
```

**Output:** Structured decision with pros/cons, all reasoning preserved.

---

### Status

**Core features implemented (Backend MVP 1.0):**
- Session branching (automatic + manual)
- Thematic blocks (AI-powered segmentation)
- Context loading from Sanctuary

**UI planned (Frontend MVP 2.0):**
- Mindmap visualization
- Minimap for long conversations
- Visual branch differentiation

---

## 🔄 Refine Mode - Iterative Refinement

**Purpose:** Create polished documents through sequential multi-agent critique

**Cognitive Mode:** Convergent, critical, iterative  
**Mental Model:** "I need to perfect this document"

---

### Key Features

**Multi-Agent Workflows (Planned):**
- Sequential critique (Writer AI → Content AI → Strategy AI)
- User reviews each iteration (Human in the Loop)
- Side-by-side comparison (see improvements)

**Iteration Stack (Planned):**
- Visual stack of all iterations
- Click to view any version
- Compare any two versions

**Agent Naming Conventions:**
- **[Domain] AI** (e.g., "Content AI", "Strategy AI", "Form AI")
- **NOT** "Lawyer", "Critic", etc. (legal safety, neutrality)

**Template System (Planned):**
- Predefined multi-agent workflows
- Customizable agent roles
- Reusable for similar tasks

---

### UI Layout (Planned)

```
┌──────────────────────────────────────────────────────┐
│ 🔄 REFINE MODE                                       │
├──────────────────────────────────────────────────────┤
│                                                      │
│  ┌─────────────┬──────────────────────────────────┐  │
│  │             │                                  │  │
│  │  LEFT       │          RIGHT                   │  │
│  │  PANEL      │          PANEL                   │  │
│  │             │                                  │  │
│  │ Iteration   │  Document + Circular Diagram     │  │
│  │ Stack       │                                  │  │
│  │             │  [Document Preview]              │  │
│  │ ● Iteration │  Research Proposal:              │  │
│  │   4 (Final) │  Urban Heat Island Mitigation... │  │
│  │ │           │                                  │  │
│  │ ├─ Iter. 3  │  [Agent Workflow]                │  │
│  │ │  Strategy │       ┌─────┐                    │  │
│  │ │           │       │ YOU │                    │  │
│  │ ├─ Iter. 2  │       └──┬──┘                    │  │
│  │ │  Content  │          │                       │  │
│  │ │           │    ┌─────┴─────┐                 │  │
│  │ ├─ Iter. 1  │ Content Writer Strategy          │  │
│  │ │  Writer   │   AI     AI      AI              │  │
│  │ │           │                                  │  │
│  │ └─ Draft    │  [Compare Versions]              │  │
│  │             │  Iteration 1 vs. Iteration 4     │  │
│  │             │                                  │  │
│  └─────────────┴──────────────────────────────────┘  │
│                                                      │
└──────────────────────────────────────────────────────┘
```

---

### When to Use

- **Legal Documents:** Organizing and structuring letters, contracts, filings (not legal advice - consult an attorney)
- **Academic Papers:** Essays, theses, research papers
- **Business Documents:** Proposals, reports, presentations
- **Technical Documentation:** API docs, user guides
- **Creative Writing:** Articles, blog posts, stories

---

### Real-World Example

```
Topic: "Climate adaptation research proposal"

1. User starts Refine Mode
2. Load context from Sanctuary: "Urban Heat Island Research Framework"
3. Multi-agent workflow:
   
   Iteration 1: Writer AI drafts proposal
   → User reviews: "Good start, but lacks methodological detail"
   
   Iteration 2: Content AI critiques
   → "Add reference to relevant theoretical frameworks"
   → "Specify data collection methods and sample sizes"
   → User reviews: "Better, but research questions need refinement"
   
   Iteration 3: Strategy AI optimizes structure
   → "Strengthen research questions and hypotheses"
   → "Add clear timeline and milestones"
   → User reviews: "Perfect!"
   
4. Save final version to Sanctuary: "Research → Proposals"
```

**Output:** Professionally written, methodologically sound, strategically structured proposal.

---

### Sequential vs. Parallel Multi-Agent

**Refine Mode = Sequential (Human in the Loop):**
```
Writer AI → Draft 1
    ↓
User reviews → Feedback
    ↓
Content AI → Draft 2
    ↓
User reviews → Feedback
    ↓
Strategy AI → Draft 3 (Final)
```

**Research Mode = Parallel (Think Tank, Future Feature):**
```
User orchestrates multiple AIs simultaneously:
- Research AI: Find primary sources
- Analysis AI: Find related studies
- Synthesis AI: Find expert opinions
→ User synthesizes all outputs
```

---

### Status

**Planned for Future**

**Backend Support:** Session branching, document versioning (already implemented)  
**Frontend Needed:** Multi-agent canvas, iteration stack, side-by-side comparison

---

## Keyboard Shortcuts

```
Ctrl+1: Sanctuary
Ctrl+2: Genesis Deck → Research Mode
Ctrl+3: Genesis Deck → Create Mode (default)
Ctrl+4: Genesis Deck → Refine Mode
Ctrl+5: Community Deck

Tab: Switch between modes (within Genesis Deck)
```

---

## Workflow Examples

### **Workflow 1: Research → Sanctuary → Create**
```
1. Research Mode: Gather facts about "JWT authentication"
2. Sanctuary: Save key findings as summaries
3. Create Mode: Load summaries as context for implementation discussion
```

### **Workflow 2: Create → Refine → Sanctuary**
```
1. Create Mode: Explore different approaches to a problem
2. Refine Mode: Refine best approach into formal document
3. Sanctuary: Save final document as template
```

### **Workflow 3: Sanctuary → Research → Refine**
```
1. Sanctuary: Load existing templates and guidelines
2. Research Mode: Find additional sources and precedents
3. Refine Mode: Create polished document with all context
```

---

## Architectural Principles

### Why Multi-Mode Design Matters

**Traditional Approaches:**

```
Single-Interface AI Tools:
├─ One chat interface for everything
├─ No specialization
├─ Manual branching (if at all)
└─ Problem: One-size-fits-all doesn't fit anyone well

Document/Note Tools:
├─ File or page-based
├─ Manual organization
├─ No branching concept
└─ Problem: Not conversation-native
```

**Genesis Deck's Approach:**
```
Three Specialized Modes:
├─ Research Mode: Systematic fact gathering
├─ Create Mode: Exploratory thinking
├─ Refine Mode: Iterative improvement
└─ All modes: AI-native, branching, persistent

Key Advantages:
✅ Branching (automatic, not manual)
✅ Multi-Mode (3 specialized interfaces)
✅ Context Loading (from Sanctuary)
✅ Multi-Agent (planned for Refine Mode)
✅ Persistent (saves to Sanctuary)
✅ AI-Native (built-in, not bolt-on)
```

---

## Learn More

- **Overall Architecture:** [../01-architecture/overview.md](../01-architecture/overview.md)
- **Sanctuary (Where knowledge is stored):** [../02-sanctuary/overview.md](../02-sanctuary/overview.md)
- **Genesis Deck (Where knowledge is created):** This document
- **Community Deck (Where knowledge is shared):** [../04-community/overview.md](../04-community/overview.md)
- **Create Mode Details:** [create-mode/message-navigation.md](create-mode/message-navigation.md), [create-mode/visual-branch-differentiation.md](create-mode/visual-branch-differentiation.md)
- **Refine Mode Details:** [refine-mode/multi-agent-canvas.md](refine-mode/multi-agent-canvas.md)

---


