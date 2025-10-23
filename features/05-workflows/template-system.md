# Template System - Predefined Multi-Agent Workflows

**Part of:** [Multi-Agent Canvas](../03-genesis-deck/refine-mode/multi-agent-canvas.md)

## Overview

Predefined multi-agent workflow templates for common use cases, enabling users to start complex workflows with one click.

## The Vision

Instead of manually configuring multi-agent workflows every time, users can select from a library of proven templates or create their own.

## Key Features

### 1. Predefined Role Combinations
**Ready-to-use agent configurations for common scenarios:**

**Research Template:**
```
Agent A: Content AI (Claude)
  - Role: Draft research documents
  - Context: Primary sources, research data
  
Agent B: Critic AI (GPT-5)
  - Role: Critique from alternative perspective
  - Context: Draft from Agent A
  
Agent C: Fact-Checker (Gemini)
  - Role: Verify citations and references
  - Context: Source citations
```

**Advanced Research Template:**
```
Agent A: Researcher (Claude)
  - Role: Synthesize findings
  - Context: Literature, data
  
Agent B: Critic (GPT-5)
  - Role: Challenge methodology
  - Context: Research draft
  
Agent C: Editor (Gemini)
  - Role: Improve clarity
  - Context: Revised draft
  
Agent D: Citations (Ollama)
  - Role: Format references
  - Context: Final draft
```

**Technical Documentation Template:**
```
Agent A: Developer (Claude)
  - Role: Write technical content
  - Context: Code, specifications
  
Agent B: Reviewer (GPT-5)
  - Role: Check accuracy
  - Context: Documentation draft
  
Agent C: UX Advocate (Gemini)
  - Role: Improve readability
  - Context: Technical draft
```

### 2. Use-Case-Specific Templates

**Business Strategy:**
- Strategist + Risk Analyst + Stakeholder Advocate + Financial Analyst

**Academic Writing:**
- Writer + Methodology Critic + Literature Reviewer + Editor

**Product Development:**
- Product Manager + Engineer + Designer + User Advocate

**Content Creation:**
- Writer + SEO Specialist + Editor + Fact-Checker

### 3. Custom Template Creation

**Users can:**
- Save their own multi-agent configurations
- Share templates with team (Collaborative Workspaces)
- Fork and modify existing templates
- Rate and review community templates

**Template Marketplace (Future):**
- Community-contributed templates
- Verified templates by experts
- Template analytics (success rates)
- Template versioning

### 4. Smart Template Suggestions

**AI-powered template recommendations:**

```
User: "I need to write a formal research document"
  ↓
System: "Suggested Template: Research Document Refinement"
  - Agent A: Content AI (draft)
  - Agent B: Critic AI (critique)
  - Agent C: Fact-Checker (verify)
  
[Use Template] [Customize] [Browse Others]
```

## Use Cases

### 1. Legal Professionals - Document Organization Workflow
**Scenario:** Legal team organizing document workflows for multiple cases

**Note:** This template demonstrates document organization capabilities.

**Without Template:**
- Manually configure 3 agents each time
- 10 minutes setup per case
- Inconsistent document structure

**With Template:**
- Load "Document Structure Workflow" template
- Quick setup
- Consistent document organization

**Result:** Substantial time savings in document preparation (documents still require professional legal review)

### 2. Research Lab - Paper Writing
**Scenario:** PhD students writing research papers

**Without Template:**
- Each student creates their own workflow
- No standardization
- Reinventing the wheel

**With Template:**
- Lab shares "Academic Paper" template
- All students use same proven workflow
- Knowledge transfer between students

### 3. Startup - Product Documentation
**Scenario:** Fast-growing startup needs consistent docs

**Without Template:**
- Each team member documents differently
- Quality varies
- No review process

**With Template:**
- "Technical Documentation" template
- Automated review workflow
- Consistent quality across team

## Template Structure

### Template Definition (YAML)
```yaml
name: "Document Structure Workflow"
description: "Three-agent workflow for organizing and structuring professional documents"
version: "1.0"
author: "TJ-VO"
category: "Research"

agents:
  - id: "drafting_ai"
    role: "Drafting AI"
    model: "claude-3-opus"
    system_prompt: "You assist in drafting and organizing document content..."
    context_sources: ["research_data", "primary_sources"]
    
  - id: "review_ai"
    role: "Review AI"
    model: "gpt-5"
    system_prompt: "You review documents for structure, clarity, and consistency..."
    context_sources: ["draft_from_drafting_ai"]
    
  - id: "citation_ai"
    role: "Citation AI"
    model: "gemini-pro"
    system_prompt: "You verify and format citations and references..."
    context_sources: ["document_citations"]

workflow:
  - step: 1
    agent: "drafting_ai"
    action: "draft"
    output_to: ["review_ai"]
    
  - step: 2
    agent: "review_ai"
    action: "critique"
    output_to: ["drafting_ai"]
    
  - step: 3
    agent: "drafting_ai"
    action: "refine"
    output_to: ["citation_ai"]
    
  - step: 4
    agent: "citation_ai"
    action: "verify"
    output_to: ["drafting_ai"]
    
  - step: 5
    agent: "drafting_ai"
    action: "finalize"
```

## Learn More
- **Multi-Agent Canvas:** [../03-genesis-deck/refine-mode/multi-agent-canvas.md](../03-genesis-deck/refine-mode/multi-agent-canvas.md)
- **Architecture Overview:** [../01-architecture/overview.md](../01-architecture/overview.md)
- **Collaborative Workspaces:** [../04-community/collaborative-workspaces.md](../04-community/collaborative-workspaces.md)

---

**Start complex workflows with one click.**
