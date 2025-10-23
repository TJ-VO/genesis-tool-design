# Separation of Concerns and Context

**Category:** Architectural Principle  
**Related:** [Cascading Critique](../03-genesis-deck/refine-mode/cascading-critique.md), [Multi-Agent Canvas](../03-genesis-deck/refine-mode/multi-agent-canvas.md), [Parallel Query Branching](../05-workflows/parallel-query-branching.md)

**Note:** This document describes the **architectural principle**. For user-facing implementations, see:
- [Multi-Agent Canvas](../03-genesis-deck/refine-mode/multi-agent-canvas.md) - Visual workflow orchestration
- [Cascading Critique](../03-genesis-deck/refine-mode/cascading-critique.md) - Multi-level review system

---

## Overview

**Separation of Concerns and Context** is a fundamental architectural principle in Genesis-Tool that ensures **AI agents operate with isolated, purpose-specific context** to prevent bias, improve quality, and enable true critical analysis.

This principle addresses a critical flaw in current AI tools: **when the same AI both creates and reviews content, it suffers from "author bias"** and cannot provide genuine critical distance.

---

## The Problem: Author Bias in AI Systems

### Current State: Single-Context AI

Most AI tools use a single AI instance for all tasks:

```
❌ Same AI writes the document
❌ Same AI reviews the document
❌ Same AI defends its own formulations
❌ No critical distance
❌ Blind spots and errors persist
```

### Real-World Example

```
User: "Write a legal objection letter"
AI: [Writes letter with aggressive tone]

User: "Review this letter"
AI: "The letter looks good. It clearly states your position."

Problem:
├─ AI defends its own work (author bias)
├─ Doesn't recognize tone is too aggressive
├─ Misses that aggressive tone will backfire
└─ User submits flawed letter → negative outcome
```

**Why This Happens:**
- AI has **full context** of writing process
- AI "remembers" its reasoning
- AI is **contextually biased** toward its own output
- AI lacks **critical distance**

---

## The Solution: Context Isolation

### Core Principle

**Each AI agent receives ONLY the context necessary for its specific task, and NO MORE.**

```
┌─────────────────────────────────────────────────┐
│  AUTHOR AI                                      │
│  Context: User request + research materials     │
│  Task: Write initial draft                      │
│  ❌ NO access to: Critique process              │
└─────────────────────────────────────────────────┘
           ↓ Produces ↓
        [Document Draft]
           ↓ Sent to ↓
┌─────────────────────────────────────────────────┐
│  CRITIC AI (Separate Instance)                  │
│  Context: Document only (no writing process)    │
│  Task: Identify issues                          │
│  ❌ NO access to: Author's reasoning            │
└─────────────────────────────────────────────────┘
```

**Result:**
- ✅ Critic has **no knowledge** of how document was created
- ✅ Critic has **no investment** in defending it
- ✅ Critic provides **genuine critical analysis**
- ✅ Quality dramatically improves

---

## Three Dimensions of Separation

### 1. Separation of Concerns (Functional)

**Definition:** Different AI agents handle different tasks.

```
AUTHOR AI:
├─ Task: Generate content
├─ Skills: Creativity, synthesis, writing
└─ Goal: Produce comprehensive draft

CRITIC AI:
├─ Task: Identify problems
├─ Skills: Analysis, fact-checking, logic
└─ Goal: Find all issues

SYNTHESIS AI:
├─ Task: Combine critiques
├─ Skills: Prioritization, organization
└─ Goal: Actionable feedback
```

**Key Insight:** Each agent is **specialized** and **optimized** for its specific concern.

---

### 2. Separation of Context (Informational)

**Definition:** Each AI agent receives only the information needed for its task.

**Example: Cascading Critique System**

```
LINE CRITIC:
├─ Context: Single line only
├─ Task: Check word choice and tone
└─ NO access to: Other lines, document structure, other critics

CONTEXT CRITIC:
├─ Context: Full document + Sanctuary facts
├─ Task: Verify factual accuracy
└─ NO access to: Other critics' findings, writing process
```

**Key Insight:** **Minimal context = Maximum focus = Better results**

---

### 3. Separation of Temporal State (Sequential)

**Definition:** AI agents operate in sequence, not simultaneously, to prevent cross-contamination.

```
Time T1: AUTHOR AI writes
    ↓
Time T2: LINE CRITIC reviews (no knowledge of T1)
    ↓
Time T3: SENTENCE CRITIC reviews (no knowledge of T1 or T2)
    ↓
Time T4: PARAGRAPH CRITIC reviews (no knowledge of T1-T3)
    ↓
Time T5: SYNTHESIS AI combines all findings
```

**Key Insight:** **Sequential isolation prevents groupthink and confirmation bias.**

---

## Why This Works: Cognitive Science Parallels

### Human Peer Review Process

Genesis-Tool's architecture mirrors **best practices in human peer review**:

```
Academic Paper Review:
├─ Author writes paper (Author AI)
├─ Reviewer 1: Methodology expert (Specialized Critic)
├─ Reviewer 2: Statistics expert (Specialized Critic)
├─ Reviewer 3: Domain expert (Specialized Critic)
├─ Editor: Synthesizes reviews (Synthesis AI)
└─ Author: Revises based on feedback (Revision AI)

Key: Reviewers DON'T see each other's reviews until after!
```

### Preventing Cognitive Biases

| Bias | How Separation Prevents It |
|------|----------------------------|
| **Confirmation Bias** | Critic has no prior hypothesis to confirm |
| **Anchoring Bias** | Critic doesn't know author's reasoning |
| **Sunk Cost Fallacy** | Critic has no investment in content |
| **Groupthink** | Critics work independently |

---

## Multi-Level Context Hierarchies

Some agents need **more context** than others, but still **isolated from each other**.

```
┌─────────────────────────────────────────────────┐
│  CONTEXT HIERARCHY                              │
│                                                 │
│  Level 1: LINE (Minimal Context)                │
│  ├─ Access: Single line only                    │
│  └─ Example: Line Critic                        │
│                                                 │
│  Level 2: SENTENCE (Local Context)              │
│  ├─ Access: Sentence + 1-2 surrounding          │
│  └─ Example: Sentence Critic                    │
│                                                 │
│  Level 3: PARAGRAPH (Section Context)           │
│  ├─ Access: Full paragraph + topic              │
│  └─ Example: Paragraph Critic                   │
│                                                 │
│  Level 4: DOCUMENT (Full Context)               │
│  ├─ Access: Entire document                     │
│  └─ Example: Document Critic                    │
│                                                 │
│  Level 5: CROSS-DOCUMENT (Extended Context)     │
│  ├─ Access: Document + Sanctuary facts          │
│  └─ Example: Context Critic                     │
└─────────────────────────────────────────────────┘
```

**Key:** **Context increases with scope, but agents remain isolated from each other.**

---

## Use Cases

### Use Case 1: Legal Document Review

**Challenge:** Legal document must be factually accurate, properly cited, and appropriately toned.

**Without Separation:**
```
Single AI:
├─ Writes document with aggressive tone
├─ Reviews own work
├─ Defends aggressive tone ("it's assertive!")
├─ Misses that tone will backfire
└─ Result: Document rejected by court
```

**With Separation:**
```
AUTHOR AI:
├─ Writes document (no review responsibility)

LINE CRITIC (isolated):
├─ Identifies aggressive words
├─ No bias toward defending them

CONTEXT CRITIC (isolated):
├─ Verifies facts against Sanctuary
├─ Finds date inconsistency

DIPLOMATIC REVIEWER (isolated):
├─ Recognizes tone inappropriate for court
├─ Suggests diplomatic alternatives

SYNTHESIS:
├─ Combines all findings
└─ Result: Comprehensive, unbiased feedback
```

---

### Use Case 2: Parallel Query Branching

**Challenge:** Answer 10 related questions without cross-contamination.

**Without Separation:**
```
Single AI:
├─ Answers question 1
├─ Answer 1 influences answer 2
├─ Answer 2 influences answer 3
├─ ...
└─ Result: Answers are not independent
```

**With Separation:**
```
10 PARALLEL BRANCHES (isolated):
├─ Branch 1: Question 1 (no knowledge of others)
├─ Branch 2: Question 2 (no knowledge of others)
├─ ...
├─ Branch 10: Question 10 (no knowledge of others)
└─ Each answer is independent and focused

SYNTHESIS:
├─ Combines answers
├─ Identifies patterns and contradictions
└─ Result: 10 focused answers + meta-insights
```

---

## Integration with Other Features

### Cascading Critique

Perfect embodiment of Separation of Concerns:

```
Each critic level:
├─ Has isolated context (line, sentence, paragraph, etc.)
├─ Has specialized responsibility
├─ Operates independently
└─ Results synthesized at end

Result: Unbiased, comprehensive review
```

### Knowledge Stratification

Context Critic needs access to stratified knowledge:

```
CONTEXT CRITIC:
├─ Access: Document + Sanctuary
├─ Can verify: Facts, Derivations, External Sources
├─ But still isolated from: Other critics

Key: Sanctuary access is SCOPED
├─ Only relevant facts for this document
├─ Not entire Sanctuary (too much context)
└─ Prevents information overload
```

### Multi-Agent Canvas

Visual tool for implementing this principle:

```
User orchestrates agents on canvas:
├─ Defines which agent sees which context
├─ Prevents cross-contamination visually
└─ Implements separation principle through UI
```

---

## Architectural Principles

### Why Separation of Concerns Matters

**Traditional Approach (Single-Context AI):**
```
One AI, one context:
├─ Writes AND critiques in same session
├─ No separation between roles
├─ Context pollution (mixed perspectives)
└─ Problem: AI can't objectively critique its own work
```

**Separated Approach (This Design):**
```
Multiple agents, isolated contexts:
├─ Author agent: Creates content
├─ Critic agents: Review independently
├─ Synthesis layer: Combines feedback
└─ No cross-contamination

Key Advantages:
✅ Separate author/critic roles (different agents)
✅ Context isolation (enforced boundaries)
✅ Specialized agents (multiple perspectives)
✅ Independent review (no cross-talk)
✅ Synthesis layer (dedicated integration)
✅ Prevents author bias (architectural design)
```

---

## Best Practices

### 1. Minimal Context Principle

**Rule:** Give agents the **minimum context** needed for their task.

```
❌ BAD: Give Line Critic full document
   - Unnecessary information
   - Slower processing
   - Risk of bias from broader context

✅ GOOD: Give Line Critic only the line
   - Focused analysis
   - Faster processing
   - No extraneous influences
```

### 2. Single Responsibility Principle

**Rule:** Each agent has **one clear responsibility**.

```
❌ BAD: "Grammar and Fact-Checking Agent"
   - Too broad
   - Conflicting priorities
   - Unclear accountability

✅ GOOD: Separate agents
   - Grammar Agent: Only grammar
   - Fact-Checking Agent: Only facts
   - Clear responsibilities
```

### 3. Late Synthesis Principle

**Rule:** Combine results **only after** all agents complete.

```
❌ BAD: Show Agent 2 what Agent 1 found
   - Agent 2 influenced by Agent 1
   - Confirmation bias
   - Groupthink

✅ GOOD: All agents work independently
   - No cross-contamination
   - Independent findings
   - Synthesis combines at end
```

---

## Conclusion

**Separation of Concerns and Context** is not just a technical pattern—it's a **fundamental architectural principle** that enables Genesis-Tool to provide **genuinely critical, unbiased analysis** that current AI tools cannot match.

**Key Benefits:**
- ✅ **Prevents author bias** (separate author/critic)
- ✅ **Improves quality** (specialized agents)
- ✅ **Enables true critique** (no investment in defending content)
- ✅ **Mirrors human best practices** (peer review process)
- ✅ **Technically enforced** (not just guidelines)

This principle powers:
- **Cascading Critique** (5-6 isolated critic levels)
- **Parallel Query Branching** (independent branches)
- **Multi-Agent Canvas** (visual orchestration)
- **Knowledge Stratification** (scoped context access)

**Genesis-Tool doesn't just use AI—it architecturally ensures AI provides the highest quality output possible.**

---

**Status:** Vision Document (Frontend MVP)
