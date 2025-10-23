# Sanctuary - Your Knowledge Treasury

---

## Overview

The **Sanctuary** (formerly "Inventory") is your persistent, private knowledge treasury. It's where all curated knowledge lives—growing over months and years, compounding in value like intellectual capital.

**Core Principle:** Knowledge is not disposable. What you learn today should serve you tomorrow, next month, and next year.

---

## The Sanctuary Metaphor

**Why "Sanctuary"?**

A sanctuary is:
- **Sacred:** Valuable, protected, respected
- **Persistent:** Built to last, not temporary
- **Private:** Your space, your rules
- **Growing:** Accumulates treasures over time

**Metaphor:** Your personal **Library of Alexandria**—but it never burns down.

---

## Core Characteristics

### **1. Persistent**
- Grows over months and years
- Never disappears (unlike chat sessions)
- Survives tool updates, migrations, backups

### **2. Curated**
- YOU decide what's valuable enough to keep
- No auto-summarization (user control)
- Quality over quantity

### **3. Structured**
- Organized by YOUR mental model (not imposed categories)
- Hierarchical folders (like a file system, but for knowledge)
- Multi-tag support (one item, multiple categories)

### **4. Protected**
- Zero-access encryption (PBKDF2 + Fernet)
- Local-first (your data, your disk)
- Full user control (export, delete, backup)

### **5. Compounding**
- Value increases over time
- Knowledge builds on knowledge
- Reusable across sessions

---

## How It Grows

The Sanctuary is fed by all Genesis Deck modes:

```
🔍 Research Mode → Summary + Q&A → Sanctuary
🎨 Create Mode → Insights + Summaries → Sanctuary
🔄 Refine Mode → Final Documents → Sanctuary
💬 Community Deck → Imported Knowledge → Sanctuary
```

**Example Growth Over Time:**

```
Month 1:
📂 Health
  └─ 📄 Vitamin D Summary

Month 6:
📂 Health
  ├─ 📁 Nutrition (15 items)
  ├─ 📁 Exercise (8 items)
  └─ 📁 Sleep (5 items)

Year 2:
📂 Health (150+ items, hierarchically organized)
  ├─ 📁 Nutrition
  │   ├─ 📁 Vitamins (20 items)
  │   ├─ 📁 Macros (15 items)
  │   └─ 📁 Meal Planning (10 items)
  ├─ 📁 Exercise
  │   ├─ 📁 Strength Training (25 items)
  │   ├─ 📁 Cardio (12 items)
  │   └─ 📁 Recovery (8 items)
  └─ 📁 Sleep (15 items)

📂 Technology (200+ items)
📂 Rights (50+ items)
📂 Finance (30+ items)
```

**This is YOUR knowledge empire. It compounds in value over time.**

---

## Key Features

### **Persistent Storage**
- Summaries, facts, insights, documents
- Cross-session reuse (load into any Genesis Deck session)
- Document linking (attach source documents)
- Version history (track changes over time)

### **AI-Powered Tagging System**
- Automatic tag suggestions based on content
- Multi-tag support (one item, multiple categories)
- Tag-based search and filtering

### **Search and Filter**
- Full-text search across all items
- Filter by type (summary, fact, document, template)
- Filter by tags (combine multiple tags)
- Sort by date, relevance, or custom order

#### **Context Loading**
- Load any item as context into Genesis Deck
- Load multiple items at once (compose context)
- Preview before loading (verify relevance)

#### **Item Versioning**
- Track changes to knowledge items over time
- Restore previous versions if needed
- See evolution of your understanding

---

### **📋 Planned (Frontend MVP 2.0)**

#### **Hierarchical Mindmap Visualization**
- Visual navigation of your knowledge tree
- Drag-and-drop organization
- Collapsible branches for focus
- Color-coding by category or priority

#### **Advanced Organization**
- Nested folders (unlimited depth)
- Smart folders (dynamic, tag-based)
- Favorites / Pinned items
- Recently accessed / Most used

#### **Knowledge Graph View**
- See connections between items
- Discover related knowledge
- Visualize knowledge clusters

---

## UI Layout (Planned)

```
┌──────────────────────────────────────────────────────┐
│ 🏛️ SANCTUARY                                         │
├──────────────────────────────────────────────────────┤
│                                                      │
│  ┌─────────────┬──────────────┬───────────────────┐  │
│  │             │              │                   │  │
│  │  LEFT       │   CENTER     │      RIGHT        │  │
│  │  PANEL      │   PANEL      │      PANEL        │  │
│  │             │              │                   │  │
│  │ Hierarchical│  Item List   │  Item Details     │  │
│  │ Mindmap     │  (Filtered)  │  + Metadata       │  │
│  │             │              │                   │  │
│  │ 📂 Health   │  📄 Vitamin D│  Title: Vitamin D │  │
│  │ ├─ Nutrition│  📄 Protein  │  Tags: Health,    │  │
│  │ ├─ Exercise │  📄 Meal Plan│        Nutrition  │  │
│  │ └─ Sleep    │              │  Created: 2025-01 │  │
│  │             │              │  Modified: 2025-03│  │
│  │ 📂 Tech     │              │  Version: 3       │  │
│  │ 📂 Rights   │              │  Source: [doc]    │  │
│  │             │              │                   │  │
│  └─────────────┴──────────────┴───────────────────┘  │
│                                                      │
└──────────────────────────────────────────────────────┘
```

---

## When to Use

### **After Research (Research Mode)**
Save structured dossiers for future reference:
```
Research Session: "Rent reduction due to construction noise"
→ Save to: Rights → Tenant Law → Rent Reduction
```

### **After Exploration (Create Mode)**
Archive key insights and decisions:
```
Chat Session: "Should I switch to TypeScript?"
→ Save summary to: Technology → Backend → TypeScript
```

### **After Refinement (Refine Mode)**
Store final documents as templates:
```
Quality Session: "Rent reduction letter"
→ Save to: Rights → Tenant Law → Templates
```

### **Daily Knowledge Building**
Build your personal knowledge base incrementally:
```
Every session → Save 1-3 valuable insights
→ After 1 year: 365-1095 knowledge items
→ After 5 years: 1825-5475 knowledge items
```

### **Long-Term Second Brain**
Create a persistent intellectual asset:
```
Year 1: Foundation (core topics)
Year 2: Expansion (new domains)
Year 3: Refinement (deeper understanding)
Year 5: Mastery (expert-level knowledge base)
```

---

## Real-World Examples

### **Example 1: Student (School Knowledge Sanctuary)**

**Use Case:** "Schulwissen-Heiligtum" (Knowledge Sanctuary for school subjects)

```
📂 Mathematics
  ├─ 📁 Grade 8
  │   ├─ 📄 Quadratic Equations
  │   ├─ 📄 Pythagorean Theorem
  │   └─ 📄 Linear Functions
  ├─ 📁 Grade 9
  │   ├─ 📄 Trigonometry
  │   └─ 📄 Probability
  └─ 📁 Grade 10
      └─ 📄 Calculus Basics

📂 Physics
  ├─ 📁 Grade 8
  │   ├─ 📄 Newton's Laws
  │   └─ 📄 Energy Conservation
  └─ 📁 Grade 9
      └─ 📄 Electricity & Magnetism
```

**Benefit:**
- Visual structure helps with learning
- AI knows context from previous grades
- Knowledge compounds (Grade 8 → Grade 9 → Grade 10 → University → Career)
- Serendipity: Cross-subject connections (Math ↔ Physics)

---

### **Example 2: Legal Professional (Legal Information Organization)**

**Note:** This example demonstrates information organization for legal professionals.

```
📂 Legal Information
  ├─ 📁 Tenant Law Resources
  │   ├─ 📄 Rent Reduction Legal Framework (reference)
  │   ├─ 📄 Termination Protection Overview
  │   ├─ 📄 Document Templates (for customization)
  │   └─ 📄 Case Law References (BGH rulings)
  ├─ 📁 Employment Law Resources
  │   ├─ 📄 Wrongful Termination Information
  │   └─ 📄 Severance Negotiation Resources
  └─ 📁 Contract Law Resources
      └─ 📄 Standard Clauses Reference Library
```

**Benefit:**
- Organized legal information (reduces research time)
- Consistent document structure (templates for common scenarios)
- Information sharing with clients (educational purposes)

---

### **Example 3: Developer (Technical Knowledge Base)**

```
📂 Technology
  ├─ 📁 Backend
  │   ├─ 📄 API Design Patterns
  │   ├─ 📄 Database Optimization
  │   ├─ 📄 Security Best Practices
  │   └─ 📄 Error Handling Strategies
  ├─ 📁 Frontend
  │   ├─ 📄 React Best Practices
  │   ├─ 📄 CSS Architecture
  │   └─ 📄 Performance Optimization
  └─ 📁 DevOps
      ├─ 📄 CI/CD Pipelines
      └─ 📄 Docker Best Practices
```

**Benefit:**
- No more "I solved this before, where was it?"
- Consistent code quality across projects
- Onboard new team members (share knowledge blocks)

---

## The Compounding Effect

### **Traditional Approach (No Sanctuary):**
```
Year 1: Learn topic A → Forget most details over time
Year 2: Re-learn topic A → Forget again
Year 3: Re-learn topic A (again)
→ Result: Wasted time, no compounding
```

### **Genesis-Tool Approach (With Sanctuary):**
```
Year 1: Learn topic A → Save to Sanctuary → Persistent reference
Year 2: Build on topic A (already in Sanctuary) → Learn topic B
Year 3: Build on A + B → Learn topic C
→ Result: Knowledge compounds, exponential growth
```

**Metaphor:** Sanctuary is your **intellectual savings account**. It earns "compound interest" (knowledge builds on knowledge).

---

## Privacy & Security

### **Zero-Access Encryption**
- All Sanctuary data is encrypted with your master password
- Encryption: PBKDF2 (100,000 iterations) + Fernet (AES-128)
- No one can read your knowledge (not even Genesis-Tool developers)

### **Local-First**
- Your data lives on YOUR disk
- No cloud dependency (works offline)
- Full control (export, delete, backup)

### **Self-Hosting**
- Run Genesis-Tool on your own server
- Use local AI models (Ollama)
- Complete data sovereignty

---

## Architectural Principles

### Why Sanctuary's Design Matters

**Traditional Approaches:**

```
Chat-Based AI Tools:
├─ Sessions disappear after use
├─ No persistence
└─ Problem: Knowledge lost

File/Document Tools:
├─ Persistent storage
├─ Manual organization
├─ AI is bolt-on (not native)
└─ Problem: Not conversation-first
```

**Sanctuary's Approach:**
```
Persistent + AI-Native + Conversation-First:
├─ Knowledge persists for years
├─ AI-native design (built-in)
├─ Conversation-first structure
├─ Zero-access encryption
├─ Hierarchical organization
├─ Cross-session context reuse
└─ Automatic version history

Key Advantages:
✅ Persistent (years, not sessions)
✅ AI-Native (built-in, not plugin)
✅ Conversation-First (not file/page-based)
✅ Zero-Access Encryption (true privacy)
✅ Hierarchical (organized, not flat)
✅ Cross-Session Reuse (load as context)
✅ Version History (automatic tracking)
```

---

## Learn More

- **Overall Architecture:** [../01-architecture/overview.md](../01-architecture/overview.md)
- **Sanctuary (Where knowledge is stored):** This document
- **Genesis Deck (Where knowledge is created):** [../03-genesis-deck/overview.md](../03-genesis-deck/overview.md)
- **Community Deck (Where knowledge is shared):** [../04-community/overview.md](../04-community/overview.md)
- **Visual Mindmap Concept:** [visual-mindmap.md](visual-mindmap.md)

---


