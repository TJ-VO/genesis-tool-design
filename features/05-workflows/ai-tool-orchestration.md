# AI Tool Orchestration - Emergent Workflows

---

## Overview

**Vision:** The AI doesn't just respond—it actively helps you navigate Genesis-Tool's features by suggesting actions, retrieving context, and guiding you through workflows.

Instead of forcing users to learn complex hotkeys or hunt for buttons, the AI becomes an **intelligent guide** that understands when to search your Sanctuary, when to pull in Community knowledge, or when to save an insight for later.

**Two Interaction Modes:**
1. **Manual Mode:** You control everything (hotkeys, buttons, commands)
2. **Guided Mode:** AI suggests actions and helps you discover features

---

## The Problem

**Current AI Tools:**
```
User: "I need to write about renewable energy"
AI: "Here's information about renewable energy..."
[User must manually remember to save, search past conversations, etc.]
```

**With Genesis-Tool (Manual Mode Only):**
```
User: "I need to write about renewable energy"
AI: "Here's information about renewable energy..."
User: [Must press Ctrl+S or click "Save to Sanctuary"]
User: [Must remember they discussed this topic 2 months ago]
User: [Must manually search and load that context]
```

**With AI Tool Orchestration (Guided Mode):**
```
User: "I need to write about renewable energy"
AI: "I found a discussion we had about renewable energy 2 months ago. 
     Should I load that context? [Yes] [No] [Show Preview]"
User: "Yes"
AI: [Loads context] "Here's what we discussed then, plus new information..."
AI: "This looks like valuable research. Should I save it to your 
     Sanctuary under 'Environment → Renewable Energy'? [Yes] [No] [Edit Category]"
```

---

## Two Interaction Modes

### **1. Manual Mode (Always Available)**

**How it works:** You control everything explicitly.

**Methods:**
- **Hotkeys:** Ctrl+S (save), Ctrl+F (search), Ctrl+1/2/3 (switch modes)
- **Buttons:** UI buttons for all actions
- **Commands:** `@save`, `@search`, `@load`

**Example:**
```
User: "Solar panels are becoming more efficient each year..."
User: [Presses Ctrl+S]
System: "Saved to Sanctuary → Environment → Solar Energy"
```

**Best for:** Power users who know exactly what they want.

---

### **2. Guided Mode (Optional, Configurable)**

**How it works:** AI suggests actions at appropriate moments.

**The AI can:**
- Search your Sanctuary for relevant past discussions
- Suggest saving valuable insights
- Recommend Community resources
- Guide you through complex workflows

**Example 1: Proactive Context Retrieval**
```
User: "I'm planning a trip to Japan"
AI: "We discussed Japan travel tips last year! Should I pull up 
     those notes? [Yes] [No]"
User: "Yes"
AI: [Loads context] "Here's what you learned about Tokyo restaurants 
     and train passes. What would you like to know more about?"
```

**Example 2: Guided Knowledge Curation**
```
User: "I just learned that meditation reduces stress by lowering 
       cortisol levels..."
AI: "That's a valuable insight! Should I save this to your Sanctuary?
     Suggested category: Health → Mental Health → Meditation
     [Save] [Edit Category] [Skip]"
User: "Save"
AI: "Saved! I also found 3 related discussions in your Sanctuary. 
     Want to see them? [Yes] [No]"
```

**Example 3: Community Discovery**
```
User: "I'm struggling to understand quantum computing"
AI: "I found a highly-rated explanation in the Community that was 
     published yesterday. Should I show it to you? [Yes] [No]"
User: "Yes"
AI: [Shows Community content] "This explanation uses simple analogies. 
     Should I save it to your Sanctuary for later? [Yes] [No]"
```

**Example 4: Cross-Layer Workflows**
```
User: "I need to write a letter about noise complaints"
AI: "We have a template for formal complaints in your Sanctuary. 
     Should I load it? [Yes] [No]"
User: "Yes"
AI: [Loads template] "I've also found 2 similar cases in the Community. 
     Should I pull those in for reference? [Yes] [No]"
User: "Yes"
AI: [Combines contexts] "Here's your template, plus examples from 
     others. Should we start in Create Mode or Refine Mode? 
     [Create] [Refine]"
```

---

## When Does AI Suggest Actions?

**Guided Mode is smart about timing:**

✅ **Good Moments to Suggest:**
- User mentions a topic they've discussed before
- User creates valuable, reusable content
- User asks a question that Community resources could answer
- User completes a complex task (suggest saving the result)

❌ **Bad Moments to Suggest:**
- Every single message (too noisy!)
- During exploratory brainstorming (don't interrupt flow)
- When user is clearly focused on one thing

**Configuration:**
```
Settings → Guided Mode:
- Frequency: [Conservative] [Balanced] [Proactive]
- Suggest context retrieval: [On] [Off]
- Suggest saving insights: [On] [Off]
- Suggest community resources: [On] [Off]
```

---

## Technical Architecture

### **AI Tool Definitions**

The AI has access to these "tools" (function calls):

**Sanctuary Tools:**
- `sanctuary_search(query)` - Search for past knowledge
- `sanctuary_load_block(block_id)` - Load specific content
- `sanctuary_save_block(content, category, tags)` - Save new knowledge

**Community Tools:**
- `community_search(query, filters)` - Search shared knowledge
- `community_get_recent(category)` - Get recent publications
- `community_preview(item_id)` - Preview before loading

**Navigation Tools:**
- `switch_mode(mode)` - Switch between Research/Create/Refine
- `create_branch(from_message)` - Create new conversation branch
- `load_context(sources)` - Combine multiple context sources

### **Permission System**

**User Control:**
- All AI suggestions require user confirmation
- User can disable Guided Mode entirely
- User can configure which suggestions to show
- User can always override AI suggestions

**Privacy:**
- AI tool calls are logged (transparency)
- User can review what AI accessed
- No automatic actions without permission

---

## Benefits

### **For New Users:**
- **Discoverability:** Learn features naturally through use
- **Reduced Overwhelm:** AI guides you step-by-step
- **Faster Onboarding:** No need to read manuals

### **For Power Users:**
- **Efficiency:** AI automates repetitive workflows
- **Serendipity:** AI surfaces forgotten knowledge
- **Flexibility:** Can always switch to Manual Mode

### **For Everyone:**
- **Democratization:** Advanced features become accessible
- **Personalization:** AI learns your preferences over time
- **Empowerment:** You stay in control, AI assists

---

## Design Principles

1. **User Control First:** AI suggests, user decides
2. **Non-Intrusive:** Suggestions at appropriate moments only
3. **Transparent:** User always knows what AI is doing
4. **Configurable:** User can tune suggestion frequency
5. **Reversible:** All actions can be undone

---

## Learn More

- **[Architecture Overview](../01-architecture/overview.md)** – The 3-layer architecture
- **[Sanctuary](../02-sanctuary/overview.md)** – Your persistent knowledge treasury
- **[Genesis Deck](../03-genesis-deck/overview.md)** – Where knowledge is created
- **[Community Deck](../04-community/overview.md)** – Global knowledge network

---

**Genesis-Tool: AI that guides, not dictates.**

