# Parallel Query Branching

**Category:** Workflow Feature  
**Related:** [Core Architecture](../01-architecture/overview.md), [Genesis Deck](../03-genesis-deck/overview.md), [Separation of Concerns](../01-architecture/separation-of-concerns.md)

---

## Overview

**Parallel Query Branching** is a workflow pattern that addresses the challenge of asking multiple related questions to an AI. Instead of asking 10 questions sequentially (slow, shallow answers) or all at once (overwhelming, unfocused answers), Genesis-Tool **automatically creates 10 parallel branches**, processes each question in isolation, and then **synthesizes the results** into a coherent whole.

This pattern leverages Genesis-Tool's **branching architecture** and **separation of concerns** principle to deliver **faster, more focused, and higher-quality responses**.

---

## The Problem

### Current State: Sequential or Batch Queries

Most AI tools force users into two suboptimal patterns:

#### **Pattern A: Sequential Questions (Slow)**
```
User: "Question 1?"
AI: [Answer 1]
User: "Question 2?"
AI: [Answer 2]
...
User: "Question 10?"
AI: [Answer 10]

Problems:
❌ Slow (10 round trips)
❌ AI context accumulates (later answers influenced by earlier)
❌ User must wait for each answer before asking next
❌ Time-consuming and tedious
```

#### **Pattern B: Batch Questions (Shallow)**
```
User: "I have 10 questions:
      1. What are Python decorators?
      2. How does async/await work?
      3. What's the difference between list and tuple?
      ...
      10. When should I use dataclasses?"

AI: [Attempts to answer all 10 at once]

Problems:
❌ Answers are superficial (AI tries to fit everything)
❌ AI "forgets" questions 7-10 (context limit)
❌ No focus on individual questions
❌ User must manually separate answers
❌ Quality suffers
```

---

## The Solution: Fork-Query-Merge Pattern

### Core Concept

```
                    [Original Session]
                           │
                    User: "I have 10 questions
                           about Python..."
                           │
                    ┌──────┴──────┐
                    │  FORK MODE  │
                    │  (Automatic)│
                    └──────┬──────┘
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
   [Branch 1]         [Branch 2]         [Branch 10]
   Q: Decorators?     Q: Async/await?    Q: Dataclasses?
        │                  │                  │
   [AI: Focused      [AI: Focused       [AI: Focused
    answer on         answer on          answer on
    decorators]       async/await]       dataclasses]
        │                  │                  │
        └──────────────────┼──────────────────┘
                           │
                    ┌──────┴──────┐
                    │ MERGE MODE  │
                    │  (Synthesis)│
                    └──────┬──────┘
                           │
                    [Unified Document]
                    - All 10 answers
                    - Coherent structure
                    - Cross-references
                    - Ready for Sanctuary
```

---

## Three Phases: Fork → Process → Merge

### Phase 1: FORK (Automatic Branching)

**User Action:**
```
User: "I have 10 questions about Python:
       1. What are decorators?
       2. How does async/await work?
       3. What's the difference between list and tuple?
       ...
       10. When should I use dataclasses?"
```

**Genesis-Tool Response:**
```
┌─────────────────────────────────────────────────┐
│  🔀 PARALLEL QUERY BRANCHING DETECTED           │
│                                                 │
│  I've detected 10 questions. Would you like me  │
│  to:                                            │
│                                                 │
│  ○ Answer sequentially (slower, contextual)     │
│  ● Create 10 parallel branches (faster, focused)│
│                                                 │
│  [Create Branches] [Answer Sequentially]        │
└─────────────────────────────────────────────────┘
```

**Result:**
```
10 branches created:
├─ Branch 1: "What are decorators?"
├─ Branch 2: "How does async/await work?"
├─ Branch 3: "What's the difference between list and tuple?"
├─ ...
└─ Branch 10: "When should I use dataclasses?"

Each branch has:
✓ Isolated context (no knowledge of other branches)
✓ Full original context (user's background)
✓ Single focused question
```

---

### Phase 2: PROCESS (Parallel Execution)

**Execution:**
```
All 10 branches process simultaneously:

Branch 1: [AI processing decorators...]      ████████░░ 80%
Branch 2: [AI processing async/await...]     ██████████ 100% ✓
Branch 3: [AI processing list vs tuple...]   ████░░░░░░ 40%
...
Branch 10: [AI processing dataclasses...]    ██████░░░░ 60%

Key: Each AI instance has NO knowledge of other branches
```

**Benefits:**
- ✅ **Faster:** All questions processed simultaneously
- ✅ **Focused:** Each AI focuses on single question
- ✅ **Independent:** No cross-contamination between answers
- ✅ **Quality:** Deep, comprehensive answers (not superficial)

---

### Phase 3: MERGE (Synthesis)

**After all branches complete:**

```
┌─────────────────────────────────────────────────┐
│  ✓ All 10 branches completed                    │
│                                                 │
│  How would you like to merge the results?       │
│                                                 │
│  ● Intelligent Synthesis                        │
│    - AI creates coherent document               │
│    - Adds structure and cross-references        │
│    - Identifies patterns and connections        │
│                                                 │
│  ○ Simple Collection                            │
│    - Q&A format (Q1, A1, Q2, A2, ...)           │
│    - No synthesis                               │
│                                                 │
│  ○ Keep Separate                                │
│    - 10 independent documents                   │
│    - No merging                                 │
│                                                 │
│  [Merge] [Keep Separate]                        │
└─────────────────────────────────────────────────┘
```

**Intelligent Synthesis Result:**
```
# Python Advanced Concepts Guide

## Introduction
[Synthesis AI creates overview connecting all 10 topics]

## 1. Decorators
[Answer from Branch 1]

## 2. Async/Await
[Answer from Branch 2]

**Note:** Decorators (see §1) can be used with async functions.

## 3. Lists vs. Tuples
[Answer from Branch 3]

...

## Cross-References
- Decorators + Async: See example in §2.3
- Dataclasses + Type Hints: See §10.2

## Summary
[Synthesis AI creates summary highlighting key patterns]
```

**Key Features:**
- ✅ **Coherent structure** (not just concatenation)
- ✅ **Cross-references** (connections between answers)
- ✅ **Patterns identified** (meta-insights)
- ✅ **Ready for Sanctuary** (well-organized knowledge)

---

## Advanced Use Cases

### Use Case 1: Research Explosion

**Scenario:** User researching complex topic, needs to explore multiple angles.

```
User: "I'm researching quantum computing. I need to understand:
       1. Basic principles
       2. Current hardware approaches
       3. Error correction methods
       4. Programming languages
       5. Real-world applications"

Genesis-Tool:
├─ Creates 5 parallel branches
├─ Each branch gets deep, focused answer
├─ Synthesis creates comprehensive research document
└─ Document saved to Sanctuary → Research → Quantum Computing
```

---

### Use Case 2: Multi-Perspective Analysis

**Scenario:** User needs to analyze problem from multiple perspectives.

```
User: "Analyze this business decision from:
       1. Financial perspective
       2. Legal perspective
       3. Ethical perspective
       4. Technical feasibility
       5. Market timing"

Genesis-Tool:
├─ Creates 5 parallel branches
├─ Each branch analyzes from single perspective
├─ No perspective influences others (independent)
├─ Synthesis identifies conflicts and synergies
└─ User gets comprehensive multi-perspective analysis
```

---

### Use Case 3: Comparative Analysis

**Scenario:** User needs to compare multiple options.

```
User: "Compare these 5 database options for my use case:
       1. PostgreSQL
       2. MongoDB
       3. Redis
       4. Cassandra
       5. DynamoDB"

Genesis-Tool:
├─ Creates 5 parallel branches
├─ Each branch evaluates single database
├─ No bias from other evaluations
├─ Synthesis creates comparison table
└─ Highlights best fit for user's use case
```

---

## Integration with Other Features

### Knowledge Stratification

```
After merge, document is stratified:
├─ FACTS: Answers from branches (marked as AI-generated)
├─ DERIVATIONS: Synthesis insights (marked as AI-derived)
└─ EXTERNAL: User can add sources later

User can then critique each layer independently
```

### Cascading Critique

```
User can run critique on merged document:
├─ Line Critic: Check each answer
├─ Context Critic: Verify facts across branches
├─ Synthesis Critic: Check cross-references
└─ Result: High-quality, verified document
```

### Separation of Concerns

```
Perfect embodiment of separation principle:
├─ Each branch: Isolated context
├─ No cross-contamination
├─ Synthesis: Separate AI instance
└─ Result: Independent, unbiased answers
```

---

## User Experience

### Progress Visualization

```
┌─────────────────────────────────────────────────┐
│  🔀 PARALLEL QUERY BRANCHING                    │
│                                                 │
│  Processing 10 branches...                      │
│                                                 │
│  ✓ Branch 1: Decorators             [Complete]  │
│  ✓ Branch 2: Async/await            [Complete]  │
│  ⏳ Branch 3: Lists vs Tuples       [80%]       │
│  ⏳ Branch 4: Generators            [60%]       │
│  ⏳ Branch 5: Context Managers      [40%]       │
│  ⏳ Branch 6: Metaclasses           [20%]       │
│  ⏳ Branch 7: Type Hints            [10%]       │
│  ⏳ Branch 8: Concurrency           [5%]        │
│  ⏳ Branch 9: Testing               [Starting]  │
│  ⏳ Branch 10: Dataclasses          [Starting]  │
│                                                 │
│  Overall Progress: ████░░░░░░░ 40%              │
│                                                 │
│  Estimated time remaining: 2 minutes            │
└─────────────────────────────────────────────────┘
```

---

### Mindmap Visualization

```
After merge, user can visualize in Sanctuary:

                [Python Advanced Concepts]
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
   [Decorators]       [Async/Await]      [Dataclasses]
        │                  │                  │
   - Syntax          - Event Loop       - Auto __init__
   - Use Cases       - Coroutines       - Type Hints
   - Examples        - Tasks            - Immutability
        │                  │                  │
        └──────────────────┼──────────────────┘
                           │
                  [Cross-References]
```

---

## Best Practices

### When to Use Parallel Query Branching

**✅ GOOD Use Cases:**
- Multiple independent questions
- Research requiring multiple angles
- Comparative analysis
- Multi-perspective evaluation
- Exploratory learning

**❌ BAD Use Cases:**
- Questions that build on each other sequentially
- Single complex question (use regular session)
- Questions requiring shared context between answers

---

### Merge Strategy Selection

**Intelligent Synthesis:**
- ✅ Use when: Answers should be connected
- ✅ Use when: Creating comprehensive document
- ✅ Use when: Saving to Sanctuary

**Simple Collection:**
- ✅ Use when: Answers are independent
- ✅ Use when: Quick reference needed
- ✅ Use when: User will organize manually

**Keep Separate:**
- ✅ Use when: Each answer is complete standalone
- ✅ Use when: User wants to process individually
- ✅ Use when: Answers go to different Sanctuary locations

---

## Conclusion

**Parallel Query Branching** transforms how users interact with AI for multi-question scenarios.

**Key Benefits:**
- ✅ **10x faster** than sequential questioning
- ✅ **Higher quality** than batch questioning
- ✅ **Independent answers** (no cross-contamination)
- ✅ **Intelligent synthesis** (coherent final document)
- ✅ **Seamless integration** with Sanctuary and other features

**This workflow pattern demonstrates Genesis-Tool's architectural advantage: branching + separation of concerns = superior results.**

---

**Status:** Vision Document (Frontend MVP)
