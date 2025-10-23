# Inventory Stratification

**Category:** Core Feature  
**Related:** [Core Architecture](../01-architecture/overview.md), [Sanctuary](../02-sanctuary/overview.md), [Inventory Lifecycle](inventory-lifecycle.md)

---

## Overview

**Inventory Stratification** is the architectural principle of organizing knowledge into three distinct epistemic layers: **Facts** (ground truth), **Derivations** (AI-generated insights), and **External Sources** (research materials).

This three-layer model solves a critical problem in long-term knowledge work: **maintaining intellectual integrity** when mixing primary sources, AI-assisted analysis, and external research over extended periods (months or years).

---

## The Problem: Epistemic Chaos

### Current State: Undifferentiated Knowledge

Most note-taking and AI tools treat all information equally, leading to:

```
❌ Facts mixed with interpretations
❌ AI-generated content indistinguishable from primary sources
❌ External research buried in personal notes
❌ Loss of provenance over time
❌ Inability to verify claims months later
```

### Real-World Pain Point: Long-Term Research Project Management

**Scenario:** Research project spanning 18 months

```
Month 1: Initial research planning (meeting notes)
Month 2: Data collection begins (raw measurements)
Month 4: Preliminary analysis (statistical results)
Month 6: AI-generated research synthesis
Month 9: Literature review (Smith et al. 2023 study)
Month 12: New data collected
Month 15: AI-generated methodology refinement
Month 18: Final analysis

Question after 18 months:
"Which parts of my research are verifiable data,
 which are AI interpretations,
 and which are external literature sources?"

Current tools: ❌ No way to distinguish
Genesis-Tool: ✅ Clear stratification
```

**Why This Matters:**
- **Scientific research:** Must distinguish data from analysis
- **Academic work:** Primary sources vs. interpretations
- **Technical work:** Observations vs. conclusions
- **Business decisions:** Facts vs. projections
- **Personal knowledge:** Experience vs. learned information

---

## The Solution: Three-Layer Epistemic Model

### Conceptual Framework

```
┌──────────────────────────────────────────────────────────┐
│  SANCTUARY (Mindmap Organization)                        │
│                                                          │
│  📁 Project: Climate Research - Urban Adaptation         │
│                                                          │
│     ├─ 🏛️ FACTS (Ground Truth)                           │
│     │   ├─ Research agreement.pdf                        │
│     │   ├─ Meeting notes: Supervisor discussion            │
│     │   ├─ Data: Field measurements                      │
│     │   ├─ Analysis results (statistical output)         │
│     │   └─ Email correspondence                          │
│     │                                                    │
│     ├─ 🧠 DERIVATIONS (AI-Generated)                     │
│     │   ├─ Research synthesis (Sep 2023)                 │
│     │   ├─ Methodology framework (Jan 2024)              │
│     │   ├─ Draft research proposal (Feb 2024)            │
│     │   └─ Gap analysis (Mar 2024)                       │
│     │                                                    │
│     └─ 📚 EXTERNAL SOURCES (Research)                    │
│         ├─ Smith et al. 2023 (primary study)             │
│         ├─ IPCC AR6 Working Group II report              │
│         ├─ Theoretical framework (Holling 1973)          │
│         └─ Policy guidelines on adaptation strategies    │
└──────────────────────────────────────────────────────────┘
```

**Key Principle:** Every piece of knowledge has an epistemic status that never changes.

---

## The Three Layers

### Layer 1: 🏛️ FACTS (Ground Truth)

**Definition:**  
Primary sources that represent objective reality or firsthand accounts.

**Characteristics:**
- ✅ Immutable (append-only, no editing)
- ✅ Timestamped
- ✅ Source-attributed
- ✅ Highest epistemic value

**Examples:**
- Official documents (contracts, court protocols, certificates)
- Memory protocols (written immediately after events)
- Photos, videos, audio recordings
- Email/letter correspondence
- Witness statements
- Medical records (primary data)
- Lab results
- Meeting minutes

**Visual Treatment:**
```
Color: Blue
Icon: 🏛️ (Temple - representing foundation)
Badge: "FACT"
Edit: Locked (append-only)
```

**Why Immutable?**
- Facts don't change; understanding of them does
- Editing facts destroys evidence trail
- Annotations can be added (as separate layer)
- Version history shows when facts were recorded

---

### Layer 2: 🧠 DERIVATIONS (AI-Generated Insights)

**Definition:**  
Interpretations, analyses, and conclusions derived from facts using AI assistance.

**Characteristics:**
- ✅ Versioned (can be revised)
- ✅ Linked to source facts
- ✅ AI-attribution (which model, when)
- ✅ Revisable as understanding evolves

**Examples:**
- Legal case information organization
- Medical symptom pattern analysis (not diagnosis - consult a physician)
- Research synthesis
- Argumentation exploration
- Risk factor identification
- Pattern recognition
- Predictive modeling exploration
- Strategic option analysis

**Visual Treatment:**
```
Color: Green
Icon: 🧠 (Brain - representing thinking)
Badge: "AI-DERIVED"
Edit: Allowed (with version history)
```

**Critical Feature: Source Linking**
```
Derivation: Legal Analysis (v1.2)

"Based on Section 535 Civil Code and the defects documented
 in photos, tenant has strong case..."

📎 Based on:
├─ FACT: Photos of defects
├─ FACT: Rental contract clause 7.2
└─ EXTERNAL: Section 535 Civil Code

🤖 Generated by: GPT-5 (2024-02-15)
📝 Revised: 2 times
```

**Why Versioned?**
- Understanding evolves over time
- New facts may change conclusions
- Different AI models may produce different insights
- User can compare versions

---

### Layer 3: 📚 EXTERNAL SOURCES (Research)

**Definition:**  
Third-party materials imported for reference (laws, papers, guidelines, etc.).

**Characteristics:**
- ✅ Source-attributed (URL, citation)
- ✅ Immutable (original content preserved)
- ✅ Can be annotated
- ✅ Searchable and linkable

**Examples:**
- Legal texts (laws, regulations)
- Court rulings (case law)
- Scientific papers
- Guidelines and standards
- Expert opinions (published)
- Books and articles
- Official statistics
- Industry reports

**Visual Treatment:**
```
Color: Orange
Icon: 📚 (Books - representing external knowledge)
Badge: "EXTERNAL"
Edit: Locked (original), annotations allowed
```

**Critical Feature: Citation Management**
```
External Source: Section 535 Civil Code

"The landlord must provide the tenant with the rental
 property in a condition suitable for contractual use..."

📖 Source: Civil Code
🔗 URL: https://www.example-law-database.com/...
📅 Version: Valid as of 2024-01-01
📌 Imported: 2024-03-10

💬 Your annotations: [3]
🔗 Cited in: [2 derivations]
```

**Why Separate from Facts?**
- External sources are not YOUR facts
- They may be disputed or change
- Attribution is critical for verification
- Different legal/epistemic status

---

## Visual Differentiation in Sanctuary

### Color-Coded Mindmap Nodes

```
Mindmap View:

📁 Case: Tenant Dispute
   │
   ├─ 🏛️ [FACT] Rental contract
   │   └─ 📅 2023-01-15
   │
   ├─ 🧠 [AI v1.2] Legal analysis
   │   ├─ 🤖 GPT-5
   │   ├─ 📎 Links to: 3 facts, 2 sources
   │   └─ 📅 2024-02-15 (revised)
   │
   └─ 📚 [EXTERNAL] Section 535 Civil Code
       ├─ 🔗 gesetze-im-internet.de
       └─ 📅 Imported 2024-03-10
```

### Relationship Visualization

```
        [FACT: Photos of defects]
                 ↓ used by
    [DERIVATION: Legal analysis v1.2]
                 ↓ cites
        [EXTERNAL: Section 535 Civil Code]
```

**Benefits:**
- Instant visual understanding of epistemic status
- Clear provenance chains
- Easy to verify claims
- Maintains intellectual integrity

---

## Workflow: From Inventory to Stratified Sanctuary

### Step 1: Data Enters Inventory

```
User imports document or completes session
↓
Lands in Inventory (flat list)
↓
Not yet stratified
```

### Step 2: AI Suggests Stratification

```
AI analyzes content:
├─ Contains primary sources? → Suggest FACT
├─ AI-generated analysis? → Suggest DERIVATION
├─ External citation? → Suggest EXTERNAL SOURCE
└─ Mixed content? → Suggest splitting
```

### Step 3: User Curates to Sanctuary

```
User reviews AI suggestion:
├─ Accept → Add to Sanctuary with stratification
├─ Modify → Change stratification or location
└─ Split → Separate into multiple stratified items
```

### Example: Mixed Content Session

```
Session: "Legal research Section 535 Civil Code"

AI detects:
├─ User's memory of landlord meeting → FACT
├─ AI-generated legal analysis → DERIVATION
└─ Quoted Section 535 Civil Code text → EXTERNAL SOURCE

AI suggests:
"Split this session into 3 stratified items?"

User accepts:
├─ FACT: "Memory: Landlord meeting 2024-02-10"
├─ DERIVATION: "Analysis: Tenant rights under §535"
└─ EXTERNAL: "Section 535 Civil Code (quoted text)"

All three added to Sanctuary → Case XY → respective layers
```

---

## Use Cases

### Use Case 1: Legal Case Management

**Challenge:** Maintain epistemic clarity over 18-month case.

**Stratification Application:**
```
FACTS (Blue):
├─ Rental contract (immutable)
├─ Court protocols (immutable)
├─ Email correspondence (immutable)
└─ Memory protocols (immutable)

DERIVATIONS (Green):
├─ Legal analysis v1.0 (Sep 2023)
├─ Legal analysis v1.1 (Jan 2024) ← Revised after new evidence
├─ Risk assessment (Feb 2024)
└─ Argumentation strategy (Mar 2024)

EXTERNAL SOURCES (Orange):
├─ Section 535 Civil Code (tenant protection law)
├─ BGH ruling Az. VIII ZR 185/18
└─ Legal commentary

Benefits:
✓ Clear what's verifiable (facts)
✓ Clear what's interpretation (derivations)
✓ Clear what's external authority (sources)
✓ Can trace reasoning from facts → derivations → conclusions
```

---

### Use Case 2: Medical Research Data Organization

**Note:** This use case demonstrates data organization capabilities for medical research.

**Challenge:** Organize medical research data while distinguishing observations from analytical interpretations.

**Stratification Application:**
```
FACTS (Blue):
├─ Lab results (raw data)
├─ Documented symptoms (recorded observations)
├─ Medical imaging (scans, X-rays)
└─ Vital signs (measurements)

DERIVATIONS (Green):
├─ AI-assisted symptom pattern analysis (not diagnosis)
├─ Treatment option exploration (not recommendations)
├─ Risk factor identification (not medical assessment)
└─ Data trend analysis (not prognosis)

EXTERNAL SOURCES (Orange):
├─ Medical guidelines (WHO, CDC)
├─ Research papers (PubMed)
├─ Drug information (FDA)
└─ Clinical trial results

Benefits:
✓ Clear separation of data from analytical exploration
✓ Organized chain of information
✓ Can update analyses without losing original data
✓ Supports medical documentation workflows (not medical decision-making)
```

---

### Use Case 3: Scientific Research

**Challenge:** Maintain integrity of research process.

**Stratification Application:**
```
FACTS (Blue):
├─ Experimental data (measurements)
├─ Observation logs
├─ Raw survey responses
└─ Equipment calibration records

DERIVATIONS (Green):
├─ Statistical analysis (AI-assisted)
├─ Pattern recognition
├─ Hypothesis generation
└─ Conclusion drafts

EXTERNAL SOURCES (Orange):
├─ Prior research papers
├─ Theoretical frameworks
├─ Standard methodologies
└─ Peer review comments

Benefits:
✓ Research integrity maintained
✓ Clear provenance for all claims
✓ Reproducible reasoning
✓ Publication-ready documentation
```

---

## Integration with Other Features

### A) Inventory Lifecycle

```
Stratification + Lifecycle:

Inventory (Uncurated):
├─ Items not yet stratified
└─ AI suggests stratification

Sanctuary (Curated):
├─ All items stratified
├─ Facts, Derivations, External Sources
└─ Clear epistemic status

Archive (Completed):
├─ Stratification preserved
└─ Historical epistemic clarity maintained
```

---

### B) AI-Assisted Curation

```
Stratification + AI:

AI analyzes new items:
├─ Detects epistemic status
├─ Suggests stratification
├─ Identifies source links
└─ Proposes Sanctuary location

User approves/modifies:
├─ One-click stratification
├─ Or: Manual classification
└─ AI learns from corrections
```

---

### C) Version History

```
Stratification + Versioning:

FACTS:
├─ Immutable (no versions)
├─ Annotations tracked separately
└─ Original always preserved

DERIVATIONS:
├─ Full version history
├─ Can compare v1.0 vs v1.2
├─ See what changed and why
└─ Linked to facts used in each version

EXTERNAL SOURCES:
├─ Original version preserved
├─ Annotations versioned
└─ Can track when source was updated
```

---

## Architectural Principles

### Why Epistemic Stratification Matters

**Traditional Approach (Undifferentiated):**
```
All knowledge treated equally:
├─ Facts mixed with interpretations
├─ AI-generated content indistinguishable from sources
├─ External research buried in notes
└─ Problem: Loss of provenance over time
```

**Stratified Approach (This Design):**
```
Three distinct epistemic layers:

🏛️ FACTS (Ground Truth)
├─ Immutable (append-only)
├─ Timestamped and attributed
└─ Highest epistemic value

🧠 DERIVATIONS (AI-Generated)
├─ Versioned (revisable)
├─ Linked to source facts
└─ AI-attributed

📚 EXTERNAL SOURCES (Research)
├─ Source-attributed (citations)
├─ Original preserved
└─ Annotatable
```

**Key Advantages:**
- ✅ **Intellectual integrity** (clear epistemic status)
- ✅ **Verifiable reasoning** (provenance chains)
- ✅ **Long-term clarity** (status never lost)
- ✅ **Professional standards** (legal, medical, scientific)
- ✅ **AI transparency** (clear what's AI-generated)

---

## Best Practices

### For Users

**Stratification Discipline:**
- ✅ Always classify new items
- ✅ Use AI suggestions as starting point
- ✅ When in doubt, ask: "Is this MY observation or someone else's?"
- ✅ Split mixed content into separate stratified items

**Fact Management:**
- ✅ Record facts immediately (memory fades)
- ✅ Never edit facts (add annotations instead)
- ✅ Include timestamps and context
- ✅ Distinguish observation from interpretation

**Derivation Management:**
- ✅ Link derivations to source facts
- ✅ Update derivations when facts change
- ✅ Keep version history
- ✅ Note which AI model generated insights

**External Source Management:**
- ✅ Always include citation
- ✅ Preserve original text
- ✅ Annotate rather than edit
- ✅ Track when source was retrieved

---

## Future Enhancements

### Smart Stratification

```
AI learns from user behavior:
├─ Recognizes stratification patterns
├─ Improves suggestions over time
├─ Auto-stratifies with high confidence
└─ Always allows user override
```

### Provenance Chains

```
Visual provenance tracking:
├─ Fact → Derivation → Conclusion
├─ Interactive graph visualization
├─ Click to see reasoning chain
└─ Verify claims instantly
```

### Cross-Project Stratification

```
Same fact used in multiple projects:
├─ One fact, multiple derivations
├─ Different interpretations visible
├─ Epistemic status consistent
└─ No duplication
```

---

## Conclusion

**Inventory Stratification** transforms Genesis-Tool from a simple note-taking system into an **epistemically rigorous knowledge management platform**.

**Key Benefits:**
- ✅ **Intellectual integrity** (facts vs. interpretations)
- ✅ **Verifiable reasoning** (provenance chains)
- ✅ **Long-term clarity** (epistemic status never lost)
- ✅ **Professional standards** (legal, medical, scientific)
- ✅ **AI transparency** (clear what's AI-generated)

**This is not just organization—it's a fundamental commitment to epistemic clarity that makes Genesis-Tool suitable for professional knowledge work where intellectual integrity matters.**

---

**Status:** Vision Document (Frontend MVP)
