# Message Navigation - VSCode-Style Minimap

**Part of:** [Architecture Overview](../../01-architecture/overview.md) - Create Mode 🌟

---

## Overview

Visual overview of entire chat sessions with instant jump navigation. Never lose orientation in long conversations.

---

## The Problem

In long AI conversations (50+ messages):
- ❌ Endless scrolling to find specific messages
- ❌ No overview of conversation structure
- ❌ Lost orientation ("Where am I?")
- ❌ Difficult to navigate between topics

---

## The Solution: VSCode-Style Minimap

```
┌─────────────────────────────────────────────────────────┐
│ Create Mode 📄                                          │
├─────────────────────────────────────────────────────────┤
│ Chat Messages                            │ Minimap      │
│                                          │              │
│ [#1] User: Tell me about...              │ ████ ← You   │
│ [#2] AI: Vitamin D is...                 │ ████ ← AI    │
│                                          │              │
│ [#3] User: What about...                 │ ████ ← You   │
│ [#4] AI: Exercise has...                 │ ████ ← AI    │
│                                          │              │
│ ... (scrollable)                         │ ████         │
│                                          │ ████         │
│                                          │  ▼           │
│                                          │  ┃  ← Current│
│                                          │  ┃           │
└──────────────────────────────────────────┴──────────────┘
```

---

## Key Features

### 1. Color-Coded Messages
- **Blue:** User messages
- **Green:** AI messages
- **Purple:** System messages (loaded context, summaries)

### 2. Visual Block Boundaries
- Thematic separators shown as horizontal lines
- Quick identification of topic changes
- Jump to block start with one click

### 3. Click-to-Jump Navigation
- Click anywhere in minimap → instant jump
- No scrolling needed
- Maintains context awareness

### 4. Scroll Indicator
- Shows current position in conversation
- Visual feedback while scrolling
- Always know where you are

### 5. Hover Preview
- Hover over minimap → preview message content
- No need to jump to see what's there
- Quick scanning of conversation

---

## Use Cases

### 1. Long Conversations
**Scenario:** 100+ message conversation about health optimization

**Without Minimap:**
- Scroll for 30 seconds to find "that vitamin thing"
- Lost overview of conversation flow
- Difficult to see topic changes

**With Minimap:**
- Glance at minimap → see all topics at once
- Click on blue/green pattern → jump to vitamin discussion
- Instant navigation

---

### 2. Topic Identification
**Scenario:** Mixed conversation about multiple topics

**Visual Pattern Recognition:**
```
████ ← Vitamin D discussion (messages 1-10)
████
────── ← Topic boundary
████ ← Exercise discussion (messages 11-20)
████
────── ← Topic boundary
████ ← Sleep discussion (messages 21-30)
████
```

**Result:** Instant visual overview of conversation structure

---

### 3. Review & Editing
**Scenario:** Need to review conversation before summarizing

**Workflow:**
1. Scroll through conversation
2. Minimap shows position
3. See topic boundaries
4. Jump back to specific sections
5. Edit messages if needed

---

## Implementation Details

### Minimap Rendering
- **Width:** 10% of screen (right side)
- **Height:** Full chat height
- **Update:** Real-time as messages arrive
- **Interaction:** Click, hover, scroll-sync

### Color Coding
```
User Message:    ████ (Blue, #4A90E2)
AI Message:      ████ (Green, #7ED321)
System Message:  ████ (Purple, #9013FE)
Block Boundary:  ──── (Gray, #E0E0E0)
```

---

## Design Evolution

### Foundation: Basic Minimap
- Color-coded messages
- Click-to-jump
- Scroll indicator

### Advanced Features
- Block boundaries
- Hover preview
- Search highlighting

---

## Learn More

- **Architecture Overview:** [../../../01-architecture/overview.md](../../01-architecture/overview.md)
- **Knowledge Mindmap:** [../../../02-sanctuary/visual-mindmap.md](../../02-sanctuary/visual-mindmap.md)

---

**See the entire structure at a glance.**

