---
layout: post
title: "Agentic E2E Test Writing - Part 2"
date: 2025-12-21
categories: [AI]
---

# Follow-up to [Agentic E2E Test Writing](/2025/12/17/agentic-e2e-test-writing.html)

I've been reading https://github.com/sarwarbeing-ai/Agentic_Design_Patterns and I can identify that I should model the review phase of my agentic e2e test writing as a reflection pattern:

```
User pastes test table
        ↓
┌─────────────────────────┐
│  1. Test Plan Parser    │
└───────────┬─────────────┘
            ↓
┌─────────────────────────┐
│  2. Plan Validator      │
└───────────┬─────────────┘
            ↓
┌─────────────────────────┐
│  3. Gap Extractor       |
|  (write to document)    │
└───────────┬─────────────┘
            ↓
┌─────────────────────────────────────────────────────┐
│  4-5. REFLECTION LOOP (max 3 iterations)            │
│                                                     │
│    ┌──────────────────────┐                         │
│    │ Implementation       │◄──── critique ────┐     │
│    │ Planner              │                   │     │
│    │ (agent_id preserved) │                   │     │
│    └──────────┬───────────┘                   │     │
│               ↓                               │     │
│    ┌──────────────────────┐                   │     │
│    │ Plan Reviewer        │                   │     │
│    │                      │                   │     │
│    │ Status: PASS/FAIL    │───── FAIL ────────┘     │
│    └──────────┬───────────┘                         │
│               │                                     │
│               ↓ PASS                                │
│         Exit Loop                                   │
└─────────────────────────────────────────────────────┘
            ↓
      Final Report
```

Still a claude code command for now. These should have a structured output but will save that for when I migrate it to something like LangGraph.