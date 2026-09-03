---
name: sg-understand-codebase
description: Map out codebase architecture, key components, dependencies, data flows, and entry points to quickly understand how a project works. Use this skill when you're onboarding into a codebase, need to understand a module before making changes, or want a quick overview of system architecture. Generates clear documentation from the code itself.
---

# Understand Codebase

When taking on a new codebase or diving deep into unfamiliar parts, your goal is to build a complete mental model of how things work without spending weeks exploring.

## Workflow

### 1. Scope the exploration
Start by asking what you need to understand:
- **Quick overview**: High-level architecture, main modules, data flow
- **Specific feature**: How does feature X work end-to-end?
- **Module deep-dive**: What does this module do and who uses it?
- **Integration points**: How do X and Y systems communicate?
- **Deployment/infrastructure**: How does this get built and deployed?

### 2. Map the architecture

Identify and document:

**Entry points**
- Main files (server.ts, app.tsx, main.kt, etc.)
- Routes and handlers
- API endpoints
- Configuration files

**Core modules**
- What does each major folder do?
- Dependencies between modules
- Shared utilities and helpers
- Design systems or components

**Data flow**
- How data enters the system
- Key transformations
- Where it's stored (database, cache, state)
- How it leaves the system (APIs, UI, events)

**External dependencies**
- Key libraries and frameworks
- Services it calls (APIs, databases, message queues)
- Configuration and environment setup

### 3. Document key patterns

Look for:
- **File structure conventions**: How are files organized?
- **Naming patterns**: What naming conventions are used?
- **Common patterns**: How are components built? How are API calls made?
- **Error handling**: How are errors caught and handled?
- **Testing approach**: How are things tested?

### 4. Create a mental model

Synthesize findings into:
- **One-page summary**: What is this codebase for and how does it work?
- **Architecture diagram** (text or visual): Component relationships
- **Key files map**: Important files and what they do
- **Gotchas & constraints**: Things that are non-obvious or important to know
- **How to extend**: Where would you add a new feature?

### 5. Present findings

Structure your output:
1. **Executive summary** (2-3 sentences): What does this do?
2. **High-level architecture**: Components and their relationships
3. **Data flow**: How information moves through the system
4. **Key files & modules**: Most important things to know
5. **Development workflow**: How to build, test, deploy
6. **Common patterns**: How things are done in this codebase
7. **Gotchas**: Non-obvious constraints or quirks
8. **Next steps**: Where to read next or what to explore

## Tips for effective exploration

- **Start wide, go deep**: Get the big picture first, then zoom into specifics
- **Follow the code**: Read actual implementations, not just docs (docs get stale)
- **Track dependencies**: Build a mental map of what calls what
- **Find the domain language**: What terms does this codebase use for its concepts?
- **Look for examples**: Tests, fixtures, and sample data tell you how things work
- **Identify the invariants**: What assumptions does the code rely on?
- **Note the gaps**: What's missing or could be clearer?

## When to use this skill

- Taking over a new project
- Before making major changes to unfamiliar code
- When onboarding new team members
- Understanding a module before refactoring
- Preparing for a handoff or knowledge transfer
- Identifying technical debt or improvement opportunities

## Output format

Be clear and practical. Use code snippets and examples. A developer reading this should be able to:
- Understand what the system does
- Find where to make a specific change
- Know what will break if they change something
- Understand the constraints and gotchas
