# Multi-Agent Canvas - Visual Workflow Orchestration

**Part of:** [Architecture Overview](../../01-architecture/overview.md) - Refine Mode 🔄

---

## Overview

The Multi-Agent Canvas enables parallel operation of multiple AI agents with different roles and precise context control. Instead of manually copying between sessions, users orchestrate agents visually on a canvas.

**Core Principle:** User controls which agents see which context, enabling sophisticated workflows without context pollution.

---

## Visual Concept

```
Canvas:
┌─────────────────────┐  ┌─────────────────────┐
│ Chat A: "Analyst"   │  │ Chat B: "Critic"    │
│ Model: Claude       │  │ Model: GPT          │
│ Context:            │  │ Context:            │
│ - Research data     │  │ - Draft from A      │
│ - Methodology       │  │ - Alternative view  │
│ - Goal: Analysis    │  │ - Goal: Critique    │
└─────────────────────┘  └─────────────────────┘
         ▲
         │ (Data)
┌────────┴────────┐
│ Chat C:         │
│ "Researcher"    │
│ Model: Gemini   │
│ Context: None   │
│ Goal: Sources   │
└─────────────────┘
         ▲
         │ (User Request)
```

---

## Killer Use Case: Research Paper Analysis

### Scenario
User creates a comprehensive analysis of competing research methodologies.

### Workflow

#### 1. Chat A: "Analyst" (Create Draft)
```
Role: Research Analyst (System Prompt)
Model: Claude 4.5 Sonnet
Context:
  - Research data (Documents)
  - Methodology framework
  - Goal: Comparative analysis

User: "Create a comparative analysis of these research methodologies"
AI (Analyst): [Draft analysis document]
```

#### 2. Chat B: "Critic" (Develop Critique)
```
Role: Critical Reviewer (System Prompt)
Model: GPT-5
Context:
  - Draft from Chat A (drag & drop)
  - Research data (factual parts only)
  - Alternative perspectives

User: "You are a critical reviewer. Identify weaknesses and gaps."
AI (Critic): [Critical analysis, methodological concerns, gaps]
```

#### 3. Chat A: "Analyst" (Refinement)
```
Context:
  - Original draft
  - Critique from Chat B (drag & drop)

User: "Refine the analysis based on the critique"
AI (Analyst): [Improved draft, gaps addressed, stronger argumentation]
```

#### 4. Chat C: "Researcher" (Fact-Check)
```
Role: Research Assistant (System Prompt)
Model: Gemini 2.5 Pro
Context: None (clean slate)

User (from Chat A): "Which studies support this conclusion?"
AI (Analyst): "Smith et al. 2023, Chen & Wang 2022, Rodriguez et al. 2024"

User (to Chat C): "Find full citations and abstracts for these studies"
AI (Researcher): [Research, full citations from academic databases]
→ Saves as documents in Sanctuary

User (to Chat A): [Loads documents via drag & drop]
AI (Analyst): [Cites studies correctly in analysis]
```

**Result:** Professional research analysis, pre-tested against critical review, with correct academic citations.

---

## Core Features

### 1. Role System

```
Each agent can have a role:
├─ Analyst (analytical, strategic)
├─ Critic (counter-perspective)
├─ Researcher (neutral, fact-focused)
├─ Editor (style, grammar)
├─ Reviewer (quality assurance)
└─ Custom roles (user-defined)

Role = System Prompt + Personality + Goals
```

### 2. Context Composition (Drag & Drop)

```
User controls what each agent sees:
├─ Drag document from Sanctuary → Chat A
├─ Drag output from Chat A → Chat B
├─ Drag facts from Chat C → Chat A
└─ Each agent has isolated, curated context
```

### 3. Model Selection per Agent

```
Different agents can use different models:
├─ Chat A: Claude 4.5 Sonnet (reasoning)
├─ Chat B: GPT-5 (critique)
├─ Chat C: Gemini 2.5 Pro (research)
└─ User picks best model for each task
```

### 4. Context Isolation

```
Key principle: Agents DON'T see each other's context

Chat A knows:
├─ Contract details
├─ User's goal
└─ ❌ NOT Chat B's counter-argument (until user shares it)

Chat B knows:
├─ Draft from Chat A (user shared)
├─ Seller perspective
└─ ❌ NOT Chat A's full context

Result: True adversarial testing, no bias
```

---

## Use Cases

### 1. Legal Documents

**Note:** This workflow demonstrates document organization capabilities.

**Workflow:**
- Drafting AI: Create initial document structure
- Review AI: Identify potential weaknesses
- Drafting AI: Refine based on review
- Citation AI: Verify legal references
- Style AI: Polish language and formatting

**Result:** Well-structured document ready for professional legal review.

---

### 2. Research Papers

**Workflow:**
- Author agent: Write paper
- Reviewer 1 agent: Methodology critique
- Reviewer 2 agent: Statistics critique
- Reviewer 3 agent: Domain expertise critique
- Author agent: Revise based on all reviews

**Result:** Publication-ready paper.

---

### 3. Business Strategy

**Workflow:**
- Strategist agent: Propose strategy
- Competitor agent: Simulate competitor response
- Market agent: Analyze market conditions
- Financial agent: Evaluate costs/benefits
- Strategist agent: Refine strategy

**Result:** Battle-tested business strategy.

---

## Design Evolution

### Foundation: Multi-Session Architecture
- Multiple sessions can exist simultaneously
- Sessions can reference each other
- Context isolation enforced

### Visual Canvas Interface
- Visual canvas for agent orchestration
- Drag & drop context sharing
- Role assignment UI

### Advanced Orchestration
- Parallel agent execution
- Automated workflows (templates)
- Agent-to-agent communication (controlled)

### Extensibility
- Agent marketplace (community-created roles)
- Workflow sharing
- Collaborative multi-user canvases

---

## Security & Privacy

### Context Isolation

```
Architectural design:
├─ Each agent has separate session
├─ No cross-session data leakage
├─ User explicitly controls all context sharing
└─ Audit trail of what was shared where
```

### Model Privacy

```
Different models for different sensitivity:
├─ Sensitive data: Local model (if available)
├─ Public data: Cloud models (faster, cheaper)
└─ User controls model selection per agent
```

### Encryption

```
All context stored encrypted:
├─ At rest: AES-256
├─ In transit: TLS 1.3
└─ User controls key management
```

---

## Design Philosophy

### 1. User in Control

```
User decides:
├─ Which agents exist
├─ What each agent sees
├─ Which models to use
├─ When agents communicate
└─ What gets saved where
```

### 2. Visual Clarity

```
Canvas makes workflows visible:
├─ See all agents at once
├─ See context flow (arrows)
├─ See agent status (active, idle, processing)
└─ Understand complex workflows at a glance
```

### 3. Iterative Refinement

```
Workflows are iterative:
├─ Draft → Critique → Refine → Repeat
├─ Each iteration improves quality
├─ User controls when to stop
└─ All versions preserved (history)
```

### 4. Privacy by Design

```
Privacy is architectural:
├─ Context isolation (enforced)
├─ Encryption (always on)
├─ User control (explicit)
└─ Data isolation by design
```

---

## Conclusion

The **Multi-Agent Canvas** transforms AI interaction from single-agent conversations to **orchestrated multi-agent workflows**.

**Key Benefits:**
- ✅ **Visual orchestration** (see the workflow)
- ✅ **Context control** (precise isolation)
- ✅ **Role specialization** (right agent for each task)
- ✅ **Adversarial testing** (pre-test arguments)
- ✅ **Privacy by design** (architectural isolation)

**This feature enables sophisticated workflows that are impossible with traditional single-agent AI tools.**

---

## Learn More

- [Cascading Critique](cascading-critique.md) - Multi-level review system
- [Separation of Concerns](../../01-architecture/separation-of-concerns.md) - Architectural foundation
- [Genesis Deck Overview](../overview.md) - Refine Mode context
