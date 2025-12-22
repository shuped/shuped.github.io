---
layout: post
title: "meta-frameworks?"
date: 2025-12-21
categories: [AI]
---

# The prompt I keep writing

```
Dispatch parallel subagents to create implementation plans for these items,
broken up by which plans could be worked on in parallel with a git-worktree
strategy. Create an overall plan that orchestrates running these plans in
the appropriate order and parallelization, including resolving the git-worktree merge.
```

I'm hand-rolling a lot of orchestration prompts now, I need to start looking for other frameworks or meta-frameworks.

# The contenders

**CrewAI** - Role-based agents with explicit task dependencies. Hierarchical and sequential process types.

**AutoGen** - Multi-agent conversations. Group chat patterns where agents coordinate.

**BMad** - Structured prompt frameworks. Workflow templates and agent definitions.

**SuperClaude** - Claude-specific agentic patterns. Persona and workflow architectures.

# Next

Digging into each of these to see how they handle the parallel-work-then-merge pattern. More interested in the design patterns they've formalized than the implementation details.
