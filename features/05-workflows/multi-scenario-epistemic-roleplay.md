# Multi-Scenario Epistemic Role-Play

**Category:** Advanced Workflow  
**Related:** [Cascading Critique](../03-genesis-deck/refine-mode/cascading-critique.md), [Separation of Concerns](../01-architecture/separation-of-concerns.md), [Parallel Query Branching](parallel-query-branching.md)

---

## Overview

**Multi-Scenario Epistemic Role-Play** is an advanced simulation system that addresses a fundamental limitation of current AI (as of October 2025): **AI struggles to model what different people know at different times**. AI tends to assume everyone shares its knowledge, leading to unrealistic simulations.

Genesis-Tool solves this through **knowledge-scoped multi-agent simulation** combined with **exhaustive scenario coverage** (best case, base case, worst case, and multiple edge cases), enabling users to prepare for any outcome.

---

## The Fundamental AI Problem (October 2025)

### Theory of Mind Deficit

```
❌ Current AI Problem: "Curse of Knowledge"

AI assumes:
├─ Everyone knows what AI knows
├─ Everyone has access to same information
├─ Everyone reasons the same way
└─ Everyone acts rationally

Reality:
├─ People have different knowledge
├─ People have different information access
├─ People reason differently
├─ People act on emotions, biases, strategies
```

### Real-World Example

```
User: "Simulate stakeholder negotiation for project funding"

❌ Naive AI (Single-Agent):
"The stakeholder will say: 'I see the data supports your approach, 
 so I'll approve the full budget request.'"

Problem:
├─ Stakeholder might not understand the technical details!
├─ Stakeholder might understand but have different priorities!
├─ Stakeholder might have budget constraints!
└─ Simulation is unrealistic → User unprepared

✅ Epistemic Role-Play (Multi-Agent):
Agent "Stakeholder":
├─ Context: Only what stakeholder ACTUALLY knows
├─ No access to: User's research, technical details
├─ Personality: Supportive but budget-conscious
└─ Behaves: Realistically

Result: Authentic, useful simulation
```

---

## The Solution: Three-Dimensional Simulation

### Dimension 1: Epistemic Isolation (Who Knows What)

```
Each agent has:
├─ Scoped knowledge (only what they know)
├─ Temporal knowledge (what they knew WHEN)
├─ No access to other agents' knowledge
└─ Realistic information asymmetry
```

### Dimension 2: Scenario Matrix (What Could Happen)

```
For every simulation, create:
├─ Best Case (optimistic outcome)
├─ Base Case (realistic outcome)
├─ Worst Case (pessimistic outcome)
└─ Edge Cases (unexpected scenarios)
```

### Dimension 3: Temporal Evolution (How It Unfolds)

```
Simulate over time:
├─ Initial state (T0)
├─ Decision points (T1, T2, T3...)
├─ Branching outcomes at each point
└─ Long-term trajectories (months/years)
```

---

## Important Note: Content Responsibility

### AI Provider Content Policies

**Content filtering is handled by the AI provider** (OpenAI, Anthropic, etc.) according to their respective content policies.

**Key Points:**
- ✅ **Provider Filtering:** Each AI provider applies their own content moderation
- ✅ **Self-Hosted Models:** No built-in filtering; user assumes full responsibility
- ✅ **Multi-Agent Systems:** Each agent is filtered by its respective provider
- ✅ **User Responsibility:** Users are responsible for their prompts and use cases

**Genesis-Tool does not add additional content filtering layers.** All content moderation is handled at the provider level.

**Transparency over paternalism:** Users should understand that scenario generation may include uncomfortable or anxiety-inducing content, depending on the prompts and the AI provider's policies.

---

## Architecture: Comprehensive Scenario Coverage

### The Scenario Matrix

```
                    [User's Situation]
                           │
                    "Negotiate project funding"
                           │
                    ┌──────┴──────┐
                    │  SCENARIO   │
                    │  GENERATOR  │
                    └──────┬──────┘
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
   [Best Case]        [Base Case]        [Worst Case]
   Full approval      Partial funding     Rejection
        │                  │                  │
   [Simulate]         [Simulate]         [Simulate]
        │                  │                  │
   [Strategy A]       [Strategy B]       [Strategy C]
        │                  │                  │
        └──────────────────┼──────────────────┘
                           │
                    ┌──────┴──────┐
                    │  SYNTHESIS  │
                    │  Multi-Path │
                    │  Response   │
                    └──────┬──────┘
                           │
                    [Comprehensive Plan]
                    - If A happens → Do X
                    - If B happens → Do Y
                    - If C happens → Do Z
```

---

## Parallel Execution via Branching

### Integration with Parallel Query Branching

```
Genesis-Tool uses parallel branching to simulate all scenarios simultaneously:

Branch 1: Best Case Simulation
├─ Agent "Stakeholder": Cooperative personality
├─ Agent "User": Prepared strategy
└─ Outcome: Full approval

Branch 2: Base Case Simulation
├─ Agent "Stakeholder": Skeptical but reasonable
├─ Agent "User": Prepared strategy
└─ Outcome: Negotiation required

Branch 3: Worst Case Simulation
├─ Agent "Stakeholder": Resistant personality
├─ Agent "User": Prepared strategy
└─ Outcome: Escalation to higher authority

All branches run simultaneously (faster)
All branches are independent (no bias)
```

---

## Adaptive Strategy Generation

### Output: Multi-Path Response Plan

```
┌─────────────────────────────────────────────────┐
│  NEGOTIATION STRATEGY: Project Funding          │
│                                                 │
│  SCENARIO A: Stakeholder is Supportive (15%)    │
│  ├─ Strategy: Direct proposal with data         │
│  ├─ Talking points: [List]                      │
│  └─ Expected outcome: Approval in 1 meeting     │
│                                                 │
│  SCENARIO B: Stakeholder is Cautious (70%)      │
│  ├─ Strategy: Phased approach                   │
│  ├─ Talking points: [List]                      │
│  ├─ Fallback positions: [List]                  │
│  └─ Expected outcome: Approval in 2-3 meetings  │
│                                                 │
│  SCENARIO C: Stakeholder is Resistant (10%)     │
│  ├─ Strategy: Escalation to leadership          │
│  ├─ Documentation needed: [List]                │
│  ├─ Alternative approaches: [List]              │
│  └─ Expected outcome: Formal review required    │
│                                                 │
│  EDGE CASES:                                    │
│  ├─ Stakeholder has budget constraints          │
│  │   └─ Response: [Strategy]                    │
│  ├─ Stakeholder offers partial funding          │
│  │   └─ Response: [Strategy]                    │
│  └─ Stakeholder requests major changes          │
│      └─ Response: [Strategy + Compromise plan]  │
│                                                 │
│  [Export to Sanctuary] [Run Simulation]         │
└─────────────────────────────────────────────────┘
```

---

## Edge Case Discovery

### AI-Assisted Edge Case Generation

```
User: "What edge cases should I consider?"

AI: [Analyzes situation and generates:]
├─ Stakeholder has budget constraints
├─ Stakeholder offers partial funding
├─ Stakeholder wants different timeline
├─ Stakeholder has competing priorities
├─ Organization has restructuring plans
├─ Other teams also requesting funding
└─ Strategic priorities shift

Each edge case gets:
├─ Probability estimate
├─ Simulated scenario
├─ Recommended response strategy
└─ Preparation checklist
```

---

## Use Cases

### Use Case 1: Stakeholder Negotiation Preparation

**Scenario:** User needs to negotiate project funding with stakeholder.

**Process:**
1. User describes situation
2. Genesis-Tool generates scenario matrix
3. Each scenario simulated with epistemic agents
4. Multi-path response plan created
5. User practices with realistic simulations

**Result:** User is prepared for any outcome.

---

### Use Case 2: Business Pitch Preparation

**Scenario:** User preparing investor pitch.

**Process:**
1. User describes pitch and investors
2. Genesis-Tool simulates:
   - Enthusiastic investor (best case)
   - Skeptical investor (base case)
   - Hostile investor (worst case)
   - Edge cases (technical questions, competitor mentions, etc.)
3. Each investor agent has realistic knowledge scope
4. User practices responses to all scenarios

**Result:** User is confident and prepared.

---

### Use Case 3: Academic Peer Review Simulation

**Scenario:** Researcher preparing paper submission.

**Process:**
1. User uploads paper
2. Genesis-Tool simulates reviewers:
   - Supportive reviewer (best case)
   - Critical but fair reviewer (base case)
   - Hostile reviewer (worst case)
3. Each reviewer has domain expertise scope
4. Identifies weaknesses before submission

**Result:** Paper is strengthened before real review.

---

## Integration with Other Features

### Cascading Critique Integration

```
After simulation:
├─ Run Cascading Critique on response plan
├─ Verify factual accuracy
├─ Check logical consistency
└─ Ensure strategies are realistic
```

### Knowledge Stratification Integration

```
Simulations use stratified knowledge:
├─ FACTS: User's documented facts
├─ DERIVATIONS: AI's strategic insights
├─ EXTERNAL: Legal/domain sources

Each agent gets appropriate knowledge scope
```

### Privacy Layer Integration

```
Simulations can involve sensitive data:
├─ PII automatically anonymized
├─ Sensitive scenarios flagged
├─ User controls what's stored
└─ Export options respect privacy
```

---

## Future Vision: When AI Costs Become Negligible (2030+)

### Unlimited Scenario Coverage

**Current (2025):** Simulate 3-5 scenarios (cost-effective)

**Future (2030+):** Simulate 100+ scenarios (exhaustive)

```
When AI inference costs approach zero:
├─ Simulate every possible edge case
├─ Explore every decision tree branch
├─ Generate comprehensive response for ANY outcome
└─ User is prepared for literally anything

Example:
├─ 50 personality variations of stakeholder
├─ 20 different negotiation strategies
├─ 30 edge cases
└─ = 30,000 simulated scenarios (all in parallel)

Result: Perfect preparation
```

---

## Conclusion

**Multi-Scenario Epistemic Role-Play** represents the future of AI-assisted preparation and planning.

**Key Benefits:**
- ✅ **Realistic simulations** (epistemic isolation)
- ✅ **Comprehensive coverage** (best/base/worst + edge cases)
- ✅ **Provider-level content policies** (OpenAI, Anthropic, etc.)
- ✅ **Multi-path strategies** (prepared for anything)
- ✅ **Parallel execution** (fast results)

**This workflow demonstrates Genesis-Tool's vision: AI that helps you prepare for reality, not just ideal scenarios.**

---

**Status:** Future Vision Document
