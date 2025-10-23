# Knowledge Mindmap - Visual Knowledge Navigation

**Part of:** [Architecture Overview](../01-architecture/overview.md) - Sanctuary 🏛️

---

## Overview

Hierarchical visualization of all Sanctuary items with drag & drop context loading. Transform your knowledge base from a flat list into an interactive, visual mindmap.

---

## The Problem

Current knowledge management in AI tools:
- ❌ Flat lists of conversations (no structure)
- ❌ Manual search through hundreds of items
- ❌ No visual relationships between knowledge
- ❌ Difficult to find related information

**Result:** Valuable knowledge gets lost in endless lists.

---

## The Solution: Visual Mindmap

```
📂 Health
  ├─ 📁 Nutrition
  │   ├─ 📄 Vitamin D Summary
  │   ├─ 📄 Protein Guide
  │   └─ 📄 Meal Planning
  │
  ├─ 📁 Exercise
  │   ├─ 📄 Workout Plan
  │   └─ 📄 Recovery Tips
  │
  └─ 📁 Sleep
      └─ 📄 Sleep Hygiene

📂 Technology
  ├─ 📁 Backend
  │   ├─ 📄 API Design Patterns
  │   └─ 📄 Database Schema Best Practices
  └─ 📁 Frontend
      ├─ 📄 React Best Practices
      └─ 📄 State Management Guide
```

---

## Key Features

### 1. Hierarchical Organization
- **Automatic topic extraction** from AI-analyzed blocks
- **Main topics → Subtopics** (e.g., "Health" → "Nutrition", "Exercise")
- **Visual tree structure** for instant overview
- **Collapsible branches** for focus

### 2. Drag & Drop Context Loading
```
User Action:
  Drag "Vitamin D Summary" from Knowledge Mindmap
  Drop into Create Mode
    ↓
Result:
  Summary loaded as context
  AI now has access to that knowledge
  No manual copy-pasting needed
```

### 3. Search Functionality

**Two Search Modes:**

**A. Cross-Session Search (Primary)**
- Search across ALL knowledge items
- Find by title, tags, or content
- Results grouped by topic
- Example: "authentication" → finds all auth-related summaries

**B. Intra-Chat Search (Secondary)**
- Search within current conversation
- Find specific message or block
- Jump to position instantly

### 4. Visual Relationships
- See which items are related (same tags)
- Color-coded by type (summary, block, document)
- Connection lines show dependencies
- Timeline view shows creation order

---

## UI Layout

```
┌─────────────────────────────────────────────────────────┐
│ Knowledge Deck 📦                                       │
├─────────────────────┬───────────────────────────────────┤
│ Left Panel          │ Right Panel                       │
│ (Mindmap Tree)      │ (Item Details)                    │
├─────────────────────┼───────────────────────────────────┤
│                     │                                   │
│ 📂 Health           │ 📄 Vitamin D Summary              │
│   ├─ 📁 Nutrition   │                                   │
│   │   ├─ 📄 Vit D   │ Created: 2025-10-15               │
│   │   ├─ 📄 Protein │ Tags: #health #nutrition #vitamin │
│   │   └─ 📄 Meals   │                                   │
│   ├─ 📁 Exercise    │ Content:                          │
│   └─ 📁 Sleep       │ Vitamin D is essential for...     │
│                     │                                   │
│ 📂 Technology       │ Sources:                          │
│   ├─ 📁 Backend     │ - Session: health-research-01     │
│   └─ 📁 Frontend    │ - Messages: 15-42                 │
│                     │                                   │
│ [Search...]         │ [Load into Chat] [Edit] [Delete]  │
│                     │                                   │
└─────────────────────┴───────────────────────────────────┘
```

---

## Use Cases

### 1. Research Project Management
**Scenario:** Working on multiple research topics over months

**Without Mindmap:**
- 50+ summaries in flat list
- Manual search for "that vitamin thing from 2 months ago"
- No overview of what you've researched

**With Mindmap:**
```
📂 Research Projects
  ├─ 📁 Health Optimization
  │   ├─ 📄 Vitamin D (Oct 15)
  │   ├─ 📄 Exercise (Oct 18)
  │   └─ 📄 Sleep (Oct 20)
  │
  └─ 📁 Backend Development
      ├─ 📄 API Design (Sep 10)
      └─ 📄 Database Schema (Sep 15)
```

**Result:** Instant overview, easy navigation, clear structure

---

### 2. Context Composition
**Scenario:** Need to combine knowledge from multiple topics

**Workflow:**
1. Open Knowledge Mindmap
2. Navigate to "Health" → "Nutrition"
3. Drag "Vitamin D Summary" to Create Mode
4. Navigate to "Health" → "Exercise"
5. Drag "Workout Plan" to Create Mode
6. Navigate to "Health" → "Sleep"
7. Drag "Sleep Hygiene" to Create Mode

**Result:** AI now has complete context from 3 different topics  
**Benefit:** Fast, visual context composition vs. manual copy-pasting

---

### 3. Knowledge Discovery
**Scenario:** "What did I learn about authentication?"

**Without Mindmap:**
- Search through 100+ conversations
- Manual filtering by date/topic
- Might miss relevant items

**With Mindmap:**
```
Search: "authentication"
  ↓
Results (grouped by topic):
📂 Technology → Backend → Security
  ├─ 📄 JWT Authentication Guide
  ├─ 📄 OAuth 2.0 Flow
  └─ 📄 Password Hashing Best Practices

📂 Technology → Frontend → Security
  └─ 📄 Secure Token Storage
```

**Result:** All auth-related knowledge in one view, grouped logically

---

## Why This Matters

### For Individual Users
- **Efficiency:** Find knowledge in seconds, not minutes
- **Overview:** See your entire knowledge base at a glance
- **Control:** Organize knowledge your way
- **Scalability:** Works with 10 items or 1000 items

### For Knowledge Workers
- **Research:** Track multiple projects simultaneously
- **Learning:** Build structured knowledge over time
- **Reference:** Quick access to past insights
- **Reuse:** Load context without repetition

---

## Implementation Details

### Automatic Topic Extraction
- AI analyzes each knowledge item
- Extracts main topic and subtopics
- Suggests placement in hierarchy
- User can override/customize

### Example:
```
Knowledge Item: "Vitamin D and Immune System"
  ↓
AI Analysis:
  Main Topic: Health
  Subtopic: Nutrition
  Tags: #vitamin #immunity #health
  ↓
Suggested Placement:
  📂 Health → 📁 Nutrition → 📄 Vitamin D Summary
```

### Drag & Drop Context Loading
```
User drags item from Mindmap to Create Mode
  ↓
Backend API Call:
  POST /sessions/{id}/inventory/load
  Body: { inventory_id: "inv_123" }
  ↓
Result:
  - Item content loaded as context
  - AI can now reference it
  - Message created: "Loaded: Vitamin D Summary"
```

---

## Visual Design

### Color Coding by Type
- 🟦 **Blue:** Summaries (compressed conversations)
- 🟩 **Green:** Topic Blocks (thematic segments)
- 🟨 **Yellow:** Documents (uploaded files)
- 🟪 **Purple:** Templates (reusable patterns)

### Icons by Category
- 🏥 Health
- 💻 Technology
- 📚 Research
- 💼 Business
- 🎨 Creative
- ⚖️ Legal

### Connection Lines
- **Solid:** Direct relationship (same session)
- **Dashed:** Indirect relationship (same tags)
- **Thick:** Frequently used together

---

## Comparison: Before vs. After

### Before (Flat List)
```
Sanctuary (50 items):
1. Vitamin D Summary
2. API Design Patterns
3. Workout Plan
4. React Best Practices
5. Sleep Hygiene
...
50. Database Schema Guide

Problem: No structure, hard to navigate
```

### After (Mindmap)
```
📂 Health (15 items)
  ├─ 📁 Nutrition (5 items)
  ├─ 📁 Exercise (5 items)
  └─ 📁 Sleep (5 items)

📂 Technology (35 items)
  ├─ 📁 Backend (20 items)
  └─ 📁 Frontend (15 items)

Solution: Clear structure, easy navigation
```

---

## Design Evolution

### Foundation: Basic Visualization
- Hierarchical tree view
- Manual organization
- Basic search

### Interactive Features
- Context loading via drag & drop
- Visual feedback
- Multi-select support

### AI-Powered Organization
- Automatic topic extraction
- Smart suggestions
- Relationship detection

### Advanced Capabilities
- Connection lines
- Timeline view
- Collaborative mindmaps

---

## Learn More

- **Architecture Overview:** [../01-architecture/overview.md](../01-architecture/overview.md)
- **Context Control Concept:** [../02-sanctuary/transclusion.md](../02-sanctuary/transclusion.md)
- **Multi-Agent Canvas:** [../03-genesis-deck/refine-mode/multi-agent-canvas.md](../03-genesis-deck/refine-mode/multi-agent-canvas.md)

---

**Stop scrolling through lists. Navigate your knowledge visually.**

