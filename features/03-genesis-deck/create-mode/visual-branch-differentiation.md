# Visual Branch Differentiation

**Part of:** [Architecture Overview](../../01-architecture/overview.md) - Create Mode 🌟

## Overview

Visually distinguish between different types of branches in the **History/Mindmap View** for instant recognition.

**Important:** This feature is for **navigation and history review**, not for the normal chat experience. During regular chatting, branch creation happens seamlessly in the background—users simply continue their conversation without interruption.

## The Problem (in History Mode)

When reviewing your conversation history in the mindmap view, you encounter two fundamentally different types of branches:
1. **Normal Branches** → Exploration, "What-If" scenarios, alternative discussion paths
2. **Summary Branches** → Compressed, distilled knowledge from longer conversations

Without visual differentiation, users can't immediately tell which branch is which when navigating their conversation history, leading to confusion and inefficient navigation.

## The Solution

Multiple visual markers to distinguish branch types at a glance:

```
Normal Branch (Exploration):
main ──────────────> alternative-scenario
     (solid line, blue)

Summary Branch (Compression):
main --------------> summary-of-main
     (dashed line, green, 📝 icon)
```

## Visual Markers

### 1. Line Styles
- **Solid lines** → Normal branches (exploration)
- **Dashed lines** → Summary branches (compression)

### 2. Icons at Branch Junctions
- 🔀 → Normal branch (alternative path)
- 📝 → Summary branch (compressed knowledge)
- 🎯 → Block-filtered branch (topic extraction)

### 3. Color Coding
- **Blue** → Normal branches
- **Green** → Summary branches
- **Purple** → Block-filtered branches

## Example in Mindmap

```
                    🔀 alternative-1 (solid, blue)
                   /
main ──────────────
                   \
                    📝 summary-v1 (dashed, green)
                     \
                      📝 summary-v2 (dashed, green)
```

## Why This Matters (for History Navigation)

- **Instant Recognition:** Know the branch type without reading labels when reviewing history
- **Better Navigation:** Quickly find summaries vs. explorations in the mindmap view
- **Reduced Cognitive Load:** Visual system does the work when you need to understand your conversation tree
- **Scalability:** Works even with 50+ branches in complex projects

**Seamless Experience:** During normal chatting, users don't see or interact with this complexity. Branch creation happens automatically in the background. This visual differentiation is only visible when users explicitly enter "History Mode" to review or navigate their conversation tree.

## Implementation

The final UI will likely combine all three approaches (line styles + icons + colors) for maximum clarity and accessibility.

## Learn More
- **Architecture Overview:** [../../../01-architecture/overview.md](../../01-architecture/overview.md)
