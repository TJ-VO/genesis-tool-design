# Inventory Lifecycle

**Category:** Core Feature  
**Related:** [Sanctuary](../02-sanctuary/overview.md), [Inventory Stratification](inventory-stratification.md), [Core Architecture](../01-architecture/overview.md)

---

## Overview

**Inventory Lifecycle** defines how knowledge flows through Genesis-Tool's dual-layer system: **Inventory** (storage) and **Sanctuary** (organization). While all data lives permanently in Inventory, users organize references to that data in Sanctuary through a visual mindmap interface.

---

## The Problem: Storage vs. Organization

### The Dual Challenge

Most knowledge tools conflate two separate concerns:

```
❌ Traditional Tools:

STORAGE + ORGANIZATION = SAME THING
├─ Files stored in folders
├─ Folder structure = organization
└─ Moving files = reorganizing

Problem: Can't separate "what exists" from "how it's organized"
```

### Real-World Pain Points

**Scenario 1: Reorganization is Destructive**
```
User wants to try different organization schemes
↓
Must move files between folders
├─ Breaks existing links
├─ Loses original structure
└─ Can't experiment freely

Need: Separate storage from organization
```

**Scenario 2: Multiple Views Impossible**
```
Document belongs to multiple projects
↓
Where to store it?
├─ Duplicate file → Sync nightmare
├─ Choose one location → Hard to find
└─ Symbolic links → Fragile

Need: One storage, multiple organizational views
```

**Scenario 3: Temporary vs. Permanent**
```
User imports 20 research papers
↓
All immediately visible in workspace
├─ Clutters interface
├─ Can't distinguish new from curated
└─ Overwhelming

Need: Staging area separate from organized knowledge
```

---

## The Solution: Dual-Layer Architecture

### Two Distinct Layers

```
┌─────────────────────────────────────────────────┐
│  📦 INVENTORY (Storage Layer)                   │
│  ├─ ALL data lives here                         │
│  ├─ Sessions (every conversation)               │
│  ├─ Summaries (AI-generated)                    │
│  ├─ Imported documents (PDFs, etc.)             │
│  ├─ Exported topic blocks                       │
│  ├─ Community retrievals (future)               │
│  └─ Structure: FLAT LIST (chronological)        │
│                                                 │
│  Purpose: PERMANENT STORAGE                     │
│  Metaphor: "Photo library" - all photos exist   │
│  User sees: List view, filters, search          │
│  Deletion: Moves to Trash (recoverable)         │
│                                                 │
└─────────────────────────────────────────────────┘
                  ↓ User organizes
┌─────────────────────────────────────────────────┐
│  🏛️ SANCTUARY (Organization Layer)              │
│  ├─ REFERENCES to Inventory items               │
│  ├─ User-created mindmap structure              │
│  ├─ Visual spatial organization                 │
│  ├─ Multiple items can reference same data      │
│  └─ Structure: MINDMAP (hierarchical)           │
│                                                 │
│  Purpose: VISUAL ORGANIZATION                   │
│  Metaphor: "Photo albums" - organize references │
│  User sees: Mindmap with nodes & connections    │
│  Deletion: Removes reference, keeps data        │
│                                                 │
│  Example:                                       │
│  📁 Health                                      │
│    └─ 📁 Nutrition                              │
│        └─ 📁 Supplements                        │
│            └─ 📁 Vitamin D                      │
│                ├─ 🔗 "VitD_study.pdf" [Inv#42]  │
│                ├─ 🔗 "Dosage research" [Inv#89] │
│                └─ 🔗 "Doctor advice" [Inv#103]  │
│                                                 │
└─────────────────────────────────────────────────┘
```

### Key Insight: References, Not Copies

**Inventory Item exists once:**
```
Inventory #42: "VitD_study.pdf"
├─ Stored once in database
├─ Encrypted with user's key
└─ Never duplicated
```

**Sanctuary can reference it multiple times:**
```
Sanctuary References:
├─ Health → Nutrition → Supplements → Vitamin D → [Inv#42]
├─ Research → Medical → Studies → [Inv#42]
└─ Projects → 2024 → Health Optimization → [Inv#42]

Same data, multiple organizational contexts!
```

---

## Lifecycle States

### State 1: INVENTORY (Uncurated)

**Purpose:** Permanent storage for all created/imported data

**What Lives Here:**
- Every session (all conversations)
- All AI-generated summaries
- All imported documents
- All exported topic blocks
- All community retrievals (future)

**Characteristics:**
```
✓ Flat chronological list
✓ Filterable (by type, date, tags)
✓ Searchable (full-text)
✓ Permanent (unless moved to Trash)
✓ No hierarchy (just exists)
```

**User Experience:**
```
┌─────────────────────────────────────────────────────┐
│  📦 INVENTORY                                       │
│                                                     │
│  [All] [Sessions] [Summaries] [Documents] [🔍]      │
│                                                     │
│  🔴 Not Yet Organized (23 items)                    │
│  ├─ Session: "Legal research Section 535 Civil Code"│
│  │   Created: 2 days ago                            │
│  │   [Add to Sanctuary] [Archive] [Delete]          │
│  │                                                  │
│  ├─ Summary: "Python decorators explained"          │
│  │   Created: 5 days ago                            │
│  │   [Add to Sanctuary] [Archive] [Delete]          │
│  │                                                  │
│  └─ Import: "Contract.pdf"                          │
│      Created: 1 week ago                            │
│      [Add to Sanctuary] [Archive] [Delete]          │
│                                                     │
│  🟢 Organized in Sanctuary (156 items)              │
│  └─ [Items with Sanctuary references]               │
│                                                     │
│  🟡 Archived (42 items)                             │
│  └─ [Completed work, cold storage]                  │
│                                                     │
│  [AI-Assist Organization]                           │
└─────────────────────────────────────────────────────┘
```

**Key Principle:** Everything enters Inventory first, then user decides how to organize.

---

### State 2: SANCTUARY (Curated)

**Purpose:** Visual organization of Inventory items via mindmap

**What Lives Here:**
- References to Inventory items
- User-created mindmap structure
- Hierarchical categories
- Visual spatial layout

**Characteristics:**
```
✓ Mindmap visualization
✓ User-defined hierarchy
✓ Multiple references to same item
✓ Stratified (Facts/Derivations/Sources)
✓ Active workspace
```

**User Experience:**
```
┌──────────────────────────────────────────────────────────┐
│  🏛️ SANCTUARY (Mindmap View)                             │
│                                                          │
│  📁 Legal                                                │
│    ├─ 📁 Case: Landlord Dispute                          │
│    │   ├─ 📁 Facts                                       │
│    │   │   └─ 🔗 Contract.pdf [Inv#42]                   │
│    │   ├─ 📁 Derivations                                 │
│    │   │   ├─ 🔗 Case analysis [Inv#89]                  │
│    │   │   └─ 🔗 Alternative args [Inv#103]              │
│    │   └─ 📁 External Sources                            │
│    │       └─ 🔗 Section 535 Civil Code research [Inv#67]│
│    │                                                     │
│    └─ 📁 Case: Contract Review                           │
│        └─ [Other references...]                          │
│                                                          │
│  📁 Personal                                             │
│    └─ 📁 Health                                          │
│        └─ 📁 Nutrition                                   │
│            └─ 📁 Supplements                             │
│                └─ 📁 Vitamin D                           │
│                    ├─ 🔗 Study [Inv#42] ← Same!          │
│                    └─ 🔗 Doctor [Inv#103]                │
│                                                          │
│  [Drag & Drop] [Create Node] [Link Item]                 │
└──────────────────────────────────────────────────────────┘
```

**Key Principle:** Sanctuary is a VIEW on Inventory, not a separate storage location.

---

### Adding to Sanctuary

```
From Inventory:

┌─────────────────────────────────────────────────┐
│  Add to Sanctuary                               │
│                                                 │
│  Item: "VitD_study.pdf" [Inventory #42]         │
│                                                 │
│  Select location(s) in Mindmap:                 │
│  ☑ Health → Nutrition → Supplements → Vitamin D │
│  ☑ Research → Medical → Studies                 │
│  ☐ Projects → 2024 → Health Optimization        │
│                                                 │
│  Stratification:                                │
│  ⦿ External Source (research material)         │
│  ○ Fact (primary source)                        │
│  ○ Derivation (AI-generated insight)            │
│                                                 │
│  💡 You can add this to multiple locations!     │
│     The document stays in Inventory once.       │
│                                                 │
│  [Add to Sanctuary] [Cancel]                    │
└─────────────────────────────────────────────────┘
```

**Result:**
- Inventory item unchanged (still at #42)
- Two Sanctuary nodes now reference it
- Deleting one reference doesn't affect the other
- Deleting both references doesn't delete from Inventory

---

### State 3: ARCHIVE (Completed)

**Purpose:** Mark completed work as inactive (but preserved)

**What Lives Here:**
- Completed projects
- Resolved cases
- Finished research
- Historical reference materials

**Characteristics:**
```
✓ Still in Inventory (data preserved)
✓ Marked as "archived" (metadata flag)
✓ Hidden from default views
✓ Searchable when needed
✓ Restorable to active state
```

**User Experience:**
```
In Sanctuary:

┌─────────────────────────────────────────────────┐
│  🏛️ Sanctuary → Legal → Case: Landlord Dispute  │
│                                                 │
│  [Case completed! Judgment received.]           │
│                                                 │
│  💡 This case appears complete.                 │
│     Archive it?                                 │
│                                                 │
│  What happens:                                  │
│  ✓ All Inventory items marked "archived"        │
│  ✓ Sanctuary node hidden from default view      │
│  ✓ Data preserved (not deleted)                 │
│  ✓ Searchable in Archive view                   │
│  ✓ Can be restored anytime                      │
│                                                 │
│  [Archive] [Keep Active] [Later]                │
└─────────────────────────────────────────────────┘
```

**Key Principle:** Archive is a STATUS, not a separate location.

---

### State 4: TRASH (Deleted, Recoverable)

**Purpose:** Safety net for accidental deletion

**What Lives Here:**
- Deleted Inventory items (recoverable period)
- Accidental deletions
- Items user might want back

**Characteristics:**
```
✓ Soft delete (data preserved)
✓ Recovery period (configurable, e.g. 30 days)
✓ Then permanent deletion
✓ Removes all Sanctuary references
```

**User Experience:**
```
User deletes from Inventory:

┌────────────────────────────────────────────────────────┐
│  Delete from Inventory?                                │
│                                                        │
│  Item: "Legal research Section 535 Civil Code" [Inv#67]│
│                                                        │
│  ⚠️  This will:                                        │
│  ├─ Move item to Trash (recoverable 30 days)           │
│  ├─ Remove ALL Sanctuary references                    │
│  └─ Then permanently delete after 30 days              │
│                                                        │
│  Sanctuary references (will be removed):               │
│  ├─ Legal → Case XY → External Sources                 │
│  └─ Research → Legal Topics                            │
│                                                        │
│  [Delete] [Cancel]                                     │
└────────────────────────────────────────────────────────┘

In Trash:

┌────────────────────────────────────────────────────────┐
│  🗑️ TRASH                                              │
│                                                        │
│  📄 "Legal research Section 535 Civil Code" [Inv#67]   │
│     Deleted: 2 days ago                                │
│     Permanent deletion in: 28 days                     │
│     [Restore] [Delete Now]                             │
│                                                        │
│  [Empty Trash] [Restore All]                           │
└────────────────────────────────────────────────────────┘
```

**Key Principle:** Deleting from Inventory removes data. Deleting from Sanctuary removes only the reference.

---

## Workflows

### Workflow 1: New Session → Sanctuary

```
1. User completes conversation
   ├─ Session automatically saved to Inventory
   └─ Status: "Not yet organized"

2. User reviews Inventory
   ├─ Sees new session in list
   ├─ AI suggests Sanctuary locations
   └─ User decides where to organize

3. User adds to Sanctuary
   ├─ Drags session to Mindmap node
   ├─ Or: "Add to Sanctuary" → Select location
   └─ Session now referenced in Sanctuary

4. Session lifecycle
   ├─ Inventory: Permanent storage
   ├─ Sanctuary: Organized reference
   └─ Can be referenced in multiple locations
```

---

### Workflow 2: Imported Document → Multiple Locations

```
1. User imports "VitD_study.pdf"
   ├─ Lands in Inventory #42
   └─ Status: "Not yet organized"

2. User adds to multiple Sanctuary locations
   ├─ Health → Nutrition → Supplements → Vitamin D
   ├─ Research → Medical → Studies
   └─ Projects → 2024 → Health Optimization

3. Document lifecycle
   ├─ Inventory: One copy (#42)
   ├─ Sanctuary: Three references
   └─ Deleting one reference doesn't affect others
```

---

### Workflow 3: Project Completion → Archive

```
1. User completes case work
   ├─ All related Inventory items still exist
   └─ Sanctuary node: "Case: Landlord Dispute"

2. User archives case materials
   ├─ Marks all related items as "archived"
   ├─ Sanctuary node hidden from default view
   └─ Data preserved in Inventory

3. Later: User needs reference
   ├─ Searches Archive
   ├─ Finds archived case
   └─ Can restore to active if needed
```

---

## Integration with Other Features

### A) Knowledge Stratification

```
Inventory + Stratification:

Inventory:
├─ Items have stratification metadata
└─ Facts, Derivations, External Sources

Sanctuary:
├─ Mindmap nodes show stratification
├─ Visual differentiation (colors, icons)
└─ Can filter by stratification type
```

---

### B) AI-Assisted Organization

```
Inventory + AI:

New items in Inventory:
├─ AI analyzes content
├─ Suggests Sanctuary locations
├─ Groups related items
└─ Learns from user decisions

User approves/modifies:
├─ One-click add to Sanctuary
├─ Or: Manual organization
└─ AI improves over time
```

---

## Use Cases

### Use Case 1: Legal Case Information Management

**Note:** This use case demonstrates information organization capabilities.

**Challenge:** Organizing case information over 18-month period.

**Lifecycle Application:**
```
Month 1-3: Active research
├─ Sessions → Inventory (automatic)
├─ User organizes → Sanctuary → Case XY
└─ Stratifies: Facts/Derivations/Sources

Month 4-15: Ongoing case work
├─ New evidence → Inventory
├─ Add to Sanctuary → Case XY
└─ Sanctuary stays organized

Month 18: Case completed
├─ Archive entire case
├─ Inventory items marked "archived"
├─ Sanctuary node hidden
└─ Searchable in Archive if needed
```

---

### Use Case 2: Research with Multiple Projects

**Challenge:** Same research paper relevant to multiple projects.

**Lifecycle Application:**
```
Import research paper:
├─ Lands in Inventory #42
└─ Status: "Not yet organized"

Add to multiple projects:
├─ Project A → Literature Review → [Inv#42]
├─ Project B → Background Research → [Inv#42]
└─ Personal → Reading List → [Inv#42]

Benefits:
├─ One storage location (Inventory)
├─ Multiple organizational contexts (Sanctuary)
└─ No duplication, no sync issues
```

---

### Use Case 3: Reorganization Without Destruction

**Challenge:** User wants to try different organization schemes.

**Lifecycle Application:**
```
Current organization:
├─ Sanctuary → By Topic → Legal → [Items]
└─ User wants to try: By Client

Experiment freely:
├─ Create new Sanctuary structure
├─ Add same Inventory items to new nodes
├─ Compare both organizations
└─ Keep what works, delete what doesn't

No data loss:
├─ Inventory unchanged
├─ Only Sanctuary references change
└─ Can revert anytime
```

---

## Architectural Principles

### Why Dual-Layer Architecture Matters

**Traditional Approach (Single-Layer):**
```
Storage = Organization
├─ Files stored in folders
├─ Folder structure = organization
├─ Moving files = reorganizing
└─ Problem: Can't separate "what exists" from "how it's organized"
```

**Dual-Layer Approach (This Design):**
```
Storage Layer (Inventory):
├─ All data exists once
├─ Flat, permanent storage
└─ No organizational assumptions

Organization Layer (Sanctuary):
├─ References to storage
├─ User-defined structure
├─ Multiple views possible
└─ Non-destructive reorganization
```

**Key Advantages:**
- ✅ **Separation of concerns** (storage vs. organization)
- ✅ **Non-destructive reorganization** (references, not moves)
- ✅ **Multiple organizational views** (same data, different contexts)
- ✅ **Experimentation-friendly** (try different structures without risk)
- ✅ **No duplication** (one storage, many references)

---

## Conclusion

**Inventory Lifecycle** transforms Genesis-Tool from a simple storage system into a **dual-layer architecture** that separates storage (Inventory) from organization (Sanctuary).

**Key Benefits:**
- ✅ **Separation of concerns** (storage vs. organization)
- ✅ **Non-destructive reorganization** (references, not moves)
- ✅ **Multiple organizational views** (same data, different contexts)
- ✅ **Natural workflow** (create → organize → archive)
- ✅ **No duplication** (one storage, many references)

**This is not just organization—it's a fundamental architectural principle that enables flexible, non-destructive knowledge management.**

---

**Status:** Vision Document (Frontend MVP)
