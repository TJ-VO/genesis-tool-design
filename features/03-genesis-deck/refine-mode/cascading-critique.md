# Cascading Critique System

**Category:** Refine Mode Feature  
**Related:** [Genesis Deck](../overview.md), [Separation of Concerns](../../01-architecture/separation-of-concerns.md), [Knowledge Stratification](../../01-architecture/inventory-stratification.md)

---

## Overview

The **Cascading Critique System** is a multi-level document review architecture that applies **granular criticism** at five distinct levels: **Line → Sentence → Paragraph → Document → Context**. Each level is handled by a separate AI agent with isolated context, ensuring unbiased, thorough review.

This system solves a critical problem in AI-assisted writing: **current AI tools provide only surface-level feedback** because the same AI that wrote the content is reviewing it, creating inherent bias and blind spots.

---

## The Problem

### Current State: Single-Pass, Biased Review

Most AI writing tools have a fundamental flaw:

```
❌ Same AI writes AND reviews
❌ "Author bias" - AI defends its own formulations
❌ Misses own errors and inconsistencies
❌ No critical distance
❌ Surface-level feedback only
```

### Real-World Pain Point: Critical Documents

**Scenario:** Legal objection letter to government agency

```
User writes with AI assistance:
"You are lying about the defects you supposedly fixed. 
This is an outrage!"

Current AI tools:
├─ Same AI that helped write it reviews it
├─ Might say "looks good" (defending own work)
├─ Misses: Tone too aggressive for official letter
├─ Misses: "lying" legally problematic
├─ Misses: No factual evidence cited
└─ Result: Letter rejected, case weakened

Genesis-Tool Cascading Critique:
├─ LINE CRITIC: "lying" → too aggressive
├─ SENTENCE CRITIC: Lacks factual basis
├─ PARAGRAPH CRITIC: No supporting evidence
├─ DOCUMENT CRITIC: Tone inappropriate for agency
├─ CONTEXT CRITIC: Contradicts earlier statement
└─ Result: Comprehensive revision suggestions
```

---

## The Solution: Five-Level Cascading Review

### Architectural Overview

```
┌────────────────────────────────────────────────┐
│  REFINE MODE: Multi-Agent Canvas               │
│                                                │
│  [Document: Objection to Rent Increase]        │
│                                                │
│  ┌──────────────────────────────────────────┐  │
│  │ Agent 1: LINE CRITIC                     │  │
│  │ Context: Single line only                │  │
│  │ Task: Word choice, clarity, precision    │  │
│  └──────────────────────────────────────────┘  │
│           ↓                                    │
│  ┌──────────────────────────────────────────┐  │
│  │ Agent 2: SENTENCE CRITIC                 │  │
│  │ Context: Single sentence + surrounding   │  │
│  │ Task: Grammar, length, internal logic    │  │
│  └──────────────────────────────────────────┘  │
│           ↓                                    │
│  ┌──────────────────────────────────────────┐  │
│  │ Agent 3: PARAGRAPH CRITIC                │  │
│  │ Context: Single paragraph                │  │
│  │ Task: Coherence, argumentation, flow     │  │
│  └──────────────────────────────────────────┘  │
│           ↓                                    │
│  ┌──────────────────────────────────────────┐  │
│  │ Agent 4: DOCUMENT CRITIC                 │  │
│  │ Context: Entire document                 │  │
│  │ Task: Structure, tone, completeness      │  │
│  └──────────────────────────────────────────┘  │
│           ↓                                    │
│  ┌──────────────────────────────────────────┐  │
│  │ Agent 5: CONTEXT CRITIC                  │  │
│  │ Context: Document + Sanctuary facts      │  │
│  │ Task: Consistency, factual accuracy      │  │
│  └──────────────────────────────────────────┘  │
│           ↓                                    │
│  ┌──────────────────────────────────────────┐  │
│  │ SYNTHESIS LAYER                          │  │
│  │ Combines all findings into report        │  │
│  └──────────────────────────────────────────┘  │
└────────────────────────────────────────────────┘
```

**Key Principle:** Each critic operates **independently** with **isolated context**, preventing bias and ensuring thorough review.

---

## The Five Critique Levels

### Level 1: LINE CRITIC

**Context:** Single line only  
**Task:** Word choice, clarity, precision, tone

**Example:**
```
Input Line:
"You are lying about the defects."

LINE CRITIC Output:
├─ Issue: "lying" too aggressive for official letter
├─ Severity: High
├─ Suggestion: "The statements regarding the defects are inaccurate"
└─ Reason: Professional tone required for legal correspondence
```

---

### Level 2: SENTENCE CRITIC

**Context:** Single sentence + 1-2 surrounding sentences  
**Task:** Grammar, sentence length, internal logic, readability

**Example:**
```
Input Sentence:
"The defects were identified on March 15, 2024, but you claim 
they were already fixed in February, which is impossible since 
we only learned about them in March."

SENTENCE CRITIC Output:
├─ Issue: Run-on sentence (too long, hard to parse)
├─ Severity: Medium
├─ Suggestion: Split into 2-3 shorter sentences
├─ Improved: "The defects were identified on March 15, 2024.
│             You claim they were already fixed in February.
│             This is impossible, as we only learned about them
│             in March."
└─ Reason: Clarity and readability
```

---

### Level 3: PARAGRAPH CRITIC

**Context:** Full paragraph  
**Task:** Coherence, argumentation, logical flow, transitions

**Example:**
```
Input Paragraph:
[3 sentences about rent increase objection]

PARAGRAPH CRITIC Output:
├─ Issue: Argument lacks supporting evidence
├─ Severity: High
├─ Suggestion: Add reference to relevant tenant law statute
├─ Improved structure:
│   1. State the problem (defects exist)
│   2. Cite legal basis (tenant protection law)
│   3. State consequence (rent reduction justified)
└─ Reason: Legal arguments require factual/legal support
```

---

### Level 4: DOCUMENT CRITIC

**Context:** Entire document  
**Task:** Overall structure, tone consistency, completeness, formatting

**Example:**
```
Input Document:
[Full objection letter]

DOCUMENT CRITIC Output:
├─ Issue: Tone shifts from professional to emotional
├─ Severity: High
├─ Location: Paragraph 3 becomes aggressive
├─ Suggestion: Maintain consistent professional tone throughout
├─ Issue: Missing formal closing (signature line)
├─ Severity: Medium
└─ Suggestion: Add "Sincerely" + signature block
```

---

### Level 5: CONTEXT CRITIC

**Context:** Document + relevant Sanctuary knowledge blocks  
**Task:** Factual accuracy, consistency with prior statements, cross-references

**Example:**
```
Input Document:
"The defects were identified on March 15, 2024."

CONTEXT CRITIC (checks Sanctuary):
├─ Finds: Earlier session states "defects on March 12, 2024"
├─ Issue: Date inconsistency
├─ Severity: Critical (factual error in legal document)
├─ Suggestion: Verify correct date, update document
└─ Reason: Factual accuracy essential for legal validity
```

---

### Level 6: DIPLOMATIC REVIEWER (Optional)

**Context:** Full document  
**Task:** Ensure diplomatic, professional tone for sensitive communications

**Example:**
```
DIPLOMATIC REVIEWER Output:
├─ Overall tone: Too confrontational for government agency
├─ Risk: May antagonize recipient, reduce cooperation
├─ Suggestions:
│   - Replace "This is an outrage" with factual statement
│   - Add conciliatory opening ("We appreciate your efforts...")
│   - End with cooperative note ("We remain open to discussion")
└─ Result: Professional, effective communication
```

---

## Synthesis: Unified Review Report

After all critics complete, a **Synthesis Layer** combines findings:

```
┌─────────────────────────────────────────────────┐
│  CASCADING CRITIQUE REPORT                      │
│                                                 │
│  Document: Objection to Rent Increase           │
│  Reviewed: October 2025                         │
│                                                 │
│  ⚠️  CRITICAL ISSUES (3)                        │
│  1. Line 12: "lying" too aggressive [Line]      │
│  2. Date inconsistency (March 15 vs 12) [Ctx]   │
│  3. Missing legal citation [Para]               │
│                                                 │
│  ⚠️  MEDIUM ISSUES (5)                          │
│  4. Sentence 8: Run-on, split needed [Sent]     │
│  5. Paragraph 3: Tone shift [Doc]               │
│  ...                                            │
│                                                 │
│  ℹ️  SUGGESTIONS (7)                            │
│  11. Add formal closing [Doc]                   │
│  12. Improve transition (Para 2→3) [Para]       │
│  ...                                            │
│                                                 │
│  [Apply All Fixes] [Review Individually]        │
└─────────────────────────────────────────────────┘
```

---

## User Experience

### Interactive Review Interface

```
┌───────────────────────────────────────────────────┐
│  Your Document (with inline critique)             │
│                                                   │
│  Dear Sir or Madam,                               │
│                                                   │
│  You are lying about the defects...               │
│  ⚠️ [LINE: "lying" too aggressive]                │
│     💡 Suggestion: "The statements are inaccurate"│
│     [Apply] [Ignore] [Edit]                       │
│                                                   │
│  The defects were identified on March 15, 2025... │
│  ⚠️ [CONTEXT: Date inconsistency with earlier]    │
│     💡 Verify: Was it March 12 or 15?             │
│     [Fix] [Ignore]                                │
│                                                   │
│  ...                                              │
└───────────────────────────────────────────────────┘
```

---

## Integration with Other Features

### Knowledge Stratification Integration

```
CONTEXT CRITIC uses stratified knowledge:
├─ FACTS: User's documented facts (dates, events)
├─ DERIVATIONS: User's conclusions
├─ EXTERNAL: Legal sources (tenant protection statutes)
└─ Verifies document against each layer
```

### Privacy Layer Integration

```
Before critique:
├─ PII automatically anonymized for AI review
├─ Critique performed on anonymized version
├─ Suggestions mapped back to original
└─ Privacy maintained throughout
```

---

## Advanced Features

### 1. Critique Intensity Levels

```
User selects intensity:

○ Light Review (Fast)
  - Line + Sentence critics only
  - ~30 seconds

● Standard Review (Balanced)
  - All 5 levels
  - ~2 minutes

○ Deep Review (Thorough)
  - All 5 levels + Diplomatic Reviewer
  - Iterative refinement
  - ~5 minutes
```

### 2. Domain-Specific Critics

```
User selects document type:

- Legal Document → Document Structure Critic (citations, tone, formatting)
- Academic Paper → Academic Critic (citations, structure)
- Medical Report → Medical Critic (terminology, accuracy)
- Business Proposal → Business Critic (clarity, persuasion)
```

---

## Use Cases

### 1. Legal Objection Letter

**Note:** This example demonstrates document review and organization capabilities.

**Challenge:** Document must be factually accurate, professionally toned, and properly structured.

**Cascading Critique Result:**
- Line Critic: Identifies potentially problematic language
- Context Critic: Checks dates against user's documented facts
- Paragraph Critic: Suggests citation improvements
- Document Critic: Reviews tone consistency
- Diplomatic Reviewer: Suggests diplomatic phrasing

**Outcome:** Well-structured document ready for professional legal review.

---

### 2. Academic Paper

**Challenge:** Must be well-structured, properly cited, logically sound.

**Cascading Critique Result:**
- Sentence Critic: Fixes complex sentences
- Paragraph Critic: Improves argumentation
- Document Critic: Checks structure (intro, methods, results, discussion)
- Context Critic: Verifies citations against Sanctuary sources

**Outcome:** Publication-ready academic paper.

---

## Architectural Principles

### Why Cascading Multi-Level Review Matters

**Traditional Approach (Single-Pass Review):**
```
One AI, one pass:
├─ Reviews entire document at once
├─ Same AI that wrote it
├─ Surface-level feedback
└─ Problem: Misses granular issues, has author bias
```

**Cascading Approach (This Design):**
```
Multiple agents, multiple levels:
├─ 5-6 specialized critics
├─ Each with isolated context
├─ Granular + holistic review
├─ Independent findings
└─ Synthesis combines all insights

Key Advantages:
✅ Granular review (line-level precision)
✅ Holistic review (document-level coherence)
✅ Independent critics (no author bias)
✅ Isolated context (no cross-contamination)
✅ Comprehensive coverage (nothing missed)
✅ Synthesis layer (unified actionable report)
```

---

## Design Evolution

### Foundation: Core Cascading Critique
- 5 basic critics (Line, Sentence, Paragraph, Document, Context)
- Simple synthesis report
- Basic UI with inline suggestions

### Enhanced User Experience
- Interactive review interface
- One-click fixes
- Critique intensity levels

### Specialized Critics
- Domain-specific critics (Legal, Academic, Medical, Business)
- Diplomatic Reviewer
- Custom critic creation

### Deep Integration
- Full Knowledge Stratification integration
- Privacy Layer integration
- Iterative refinement workflows

---

## Conclusion

The **Cascading Critique System** represents a fundamental advancement in AI-assisted writing: **multi-level, unbiased review** that catches what single-pass systems miss.

**Key Benefits:**
- ✅ **Granular precision** (line-level review)
- ✅ **Holistic coherence** (document-level review)
- ✅ **No author bias** (separate critics)
- ✅ **Comprehensive coverage** (5-6 levels)
- ✅ **Actionable feedback** (synthesis report)

**This system ensures that critical documents—legal letters, academic papers, medical reports—receive the thorough, unbiased review they deserve.**

---

## Related Concepts

- [Separation of Concerns](../../01-architecture/separation-of-concerns.md) - Architectural foundation
- [Multi-Agent Canvas](multi-agent-canvas.md) - Visual workflow tool
- [Knowledge Stratification](../../01-architecture/inventory-stratification.md) - Context source for critics
