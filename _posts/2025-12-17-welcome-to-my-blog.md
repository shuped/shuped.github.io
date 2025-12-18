---
layout: post
title: "Hello World"
date: 2025-12-17
categories: [AI]
---

# Agenticaly creating end to end tests from a manual QA plan

A rudimentary solution:

```
A sequential slash command `/analyze-tests` that processes test cases through a pipeline of specialized agents, producing a validated test plan and implementation guide.

User pastes test table
        ↓
┌─────────────────────────┐
│  1. Test Plan Parser    │  Normalizes input into structured markdown
└───────────┬─────────────┘
            ↓
┌─────────────────────────┐
│  2. Plan Validator      │  Code analysis + Playwright MCP
└───────────┬─────────────┘  Marks each test: Implementable / Not Testable / Not Practical
            ↓
┌─────────────────────────┐
│  3. Gap Extractor       │  Verifies claims, corrects plan, appends confirmed gaps
└───────────┬─────────────┘
            ↓
┌─────────────────────────┐
│  4. Implementation      │  Uses superpowers:writing-plans skill
│     Planner             │  Creates docs/plans/ document
└───────────┬─────────────┘
            ↓
┌─────────────────────────┐
│  5. Plan Reviewer       │  Reviews for weak tests, bad habits
└───────────┬─────────────┘  Uses e2e/CLAUDE.md as quality standard
            ↓
      Final Report / Sub-agent driven development
```

If the plan was large and well understood, I'd automate the test plan scraping and create a harness that could loop this. As it is, that's why the gap extractor is there. This is creating a document for test cases / functionality that needs more investigation (e.g. functionality doesn't actually exist or is deprecated).

I don't like that this is just a claude code command, I'd like to start building these quickly in a more scalable platform. Will have to investigate langchain etc. After all, everyone and their uncle is building an agentic code tool, I guess I should too.