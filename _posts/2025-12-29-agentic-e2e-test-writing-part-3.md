---
layout: post
title: "Agentic E2E Test Writing - Part 3"
date: 2025-12-29
categories: [AI]
---

# Migrating to LangGraph

Follow-up to [Part 2](/2025/12/21/agentic-e2e-test-writing-part-2.html).

We've migrated the Claude Code slash command to LangGraph, and added auto implementation:
```
                    ┌────────────┐
                    │   PARSER   │  Parse markdown table into structured format
                    └────────────┘
                        │
                        ▼
                    ┌────────────┐
                    │ VALIDATOR  │  Classify tests: implementable, not testable, not practical
                    └────────────┘
                        │
                        ▼
                    ┌────────────┐
                    │ EXTRACTOR  │  Verify gap claims and extract to gap-analysis doc
                    └────────────┘
                        │
                        ▼
    ┌───────────────────────────────────────┐
    │       REFLECTION LOOP (max 5)         │
    │                                       │
    │    ┌──────────┐       ┌──────────┐    │
    │    │ PLANNER  │──────▶│ REVIEWER │    │
    │    └──────────┘       └──────────┘    │
    │         ▲                   │         │
    │         │     FAIL          │         │  Create and refine implementation plan
    │         └───────────────────┘         │
    │                                       │
    └───────────────────────────────────────┘
                        │ PASS
                        ▼
                ┌─────────────┐
                │ IMPLEMENTER │  Implement plan with subagent-driven development
                └─────────────┘
                        │
                        ▼
                ┌─────────────┐
                │ TEST RUNNER │  Run e2e suite until 3 consecutive passes
                └─────────────┘
                        │
                        ▼
                ┌────────────┐
                │  REPORTER  │  Generate final summary report
                └────────────┘
```

The failure paths all proceed to reporter immediately, but the added structure from LangGraph will help make these more robust in the future. I know Graph is in the name and I've seen it before, but implementing one finally internalized for me that you are, in fact, building a graph, not an imperitive flow.