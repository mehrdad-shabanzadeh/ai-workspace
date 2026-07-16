# AI Workspace

This repository is the source of truth for reusable AI assets: prompts, context packs, agent specs, workflows, decision logs, templates, handoff packets, examples, and important outputs.

This repository is not for storing raw chats. Raw chats are noisy and hard to reuse. The goal is to extract durable knowledge assets from ChatGPT, Claude, Gemini, agents, and other AI tools, then organize and version them.

---

## Core Principle

AI tools are execution environments.  
This repository is the source of truth.

```text
ChatGPT = execution environment
Claude = execution environment
Agents = execution environment
GitHub repo = source of truth
```

Chats are temporary.  
Reusable assets are permanent.

```text
Chat → Distill → Save → Version → Reuse
```

---

## What Belongs Here

### Store These

- Reusable prompts
- Project context packs
- Agent specifications
- Multi-step workflows
- Decision logs
- Output templates
- Handoff packets between AI tools
- Tested prompt examples
- Important final outputs
- Notes that affect future AI work

### Do Not Store These

- Raw chat transcripts
- One-off answers
- Temporary drafts
- Small translation or rewriting tasks
- Large files
- Random PDFs, images, spreadsheets, or source files
- Anything unlikely to be reused

Rule:

```text
If the probability of reuse is below 20%, do not save it.
```

---

## Repository Structure

```text
ai-workspace/
  inbox/
  prompts/
  contexts/
  agents/
  workflows/
  templates/
  decisions/
  outputs/
  examples/
```

---

## Directory Guide

### `inbox/`

Temporary holding area for raw or partially processed material.

Use this when something may be valuable, but it is not yet clear where it belongs.

Example:

```text
inbox/2026-01-15-chatgpt-pricing-idea.md
```

The inbox should be reviewed and cleaned regularly.

---

### `prompts/`

Reusable prompts organized by domain or task type.

Examples:

```text
prompts/research/market-analysis.v1.md
prompts/sales/cold-email.v2.md
prompts/writing/landing-page-review.v1.md
prompts/analysis/file-summary.v1.md
```

A prompt should be self-contained, understandable, and reusable.

---

### `contexts/`

Stable background information that AI tools need.

A prompt is the instruction.  
A context pack is the background knowledge.

Examples:

```text
contexts/company/brand-voice.v1.md
contexts/projects/product-x/context.v1.md
contexts/personal/preferences.v1.md
```

---

### `agents/`

Agent definitions and operating specs.

An agent inside ChatGPT, Claude, or another platform may not be fully portable.  
The agent specification should be portable.

Examples:

```text
agents/portable/research-analyst.v1.md
agents/chatgpt/content-strategist.v1.md
agents/claude/editorial-reviewer.v1.md
```

---

### `workflows/`

Multi-step processes that combine prompts, context packs, agents, tools, and review steps.

Examples:

```text
workflows/content-production/blog-production.v1.md
workflows/research/competitor-analysis.v1.md
workflows/product/feature-discovery.v1.md
```

A workflow describes the sequence.  
Prompts are the components.

---

### `templates/`

Standard templates for reusable file types.

Examples:

```text
templates/prompt-template.md
templates/context-pack-template.md
templates/agent-spec-template.md
templates/handoff-packet-template.md
templates/decision-log-template.md
templates/workflow-template.md
```

---

### `decisions/`

Important decisions that may affect future work.

Examples:

```text
decisions/2026/2026-01-15-positioning-model.md
decisions/2026/2026-01-20-pricing-direction.md
```

A decision log should explain what was decided, why it was decided, which alternatives were rejected, and what the implications are.

---

### `outputs/`

Important final outputs worth keeping.

Examples:

```text
outputs/2026/2026-01-15-market-analysis-product-x.md
outputs/2026/2026-01-20-landing-page-copy-v1.md
```

Temporary outputs should not be saved here.

---

### `examples/`

Test cases and examples for prompts and workflows.

Examples:

```text
examples/prompt-tests/market-analysis/input.good-fit.md
examples/prompt-tests/market-analysis/output.good-fit.md
examples/prompt-tests/market-analysis/input.bad-fit.md
examples/prompt-tests/market-analysis/output.bad-fit.md
```

Examples help evaluate whether a prompt is improving or degrading over time.

---

## File Naming Convention

Recommended format:

```text
prompt.[domain].[task].v[number].md
context.[project].[topic].v[number].md
agent.[function].v[number].md
workflow.[process].v[number].md
decision.[date].[topic].md
output.[date].[topic].md
```

Examples:

```text
prompt.research.market-analysis.v1.md
prompt.sales.cold-email.v2.md
context.company.brand-voice.v3.md
agent.research-analyst.v1.md
workflow.blog-production.v2.md
decision.2026-01-15-pricing-model.md
output.2026-01-15-market-analysis.md
```

---

## Prompt Template

```markdown
# prompt.domain.task.v1

## Purpose

What this prompt is used for.

## Use When

When this prompt should be used.

## Inputs

- Input 1
- Input 2
- Input 3

## Prompt

The full prompt goes here.

## Output Format

The expected structure of the output.

## Works Best In

- ChatGPT:
- Claude:
- Other:

## Notes

Operational notes, weaknesses, constraints, and known issues.

## Version History

- v1: Initial version
```

---

## Context Pack Template

```markdown
# context.project.topic.v1

## Project / Entity

Project, company, product, or topic name.

## Goal

Main objective.

## Background

Relevant background information.

## Audience

Target audience or users.

## Constraints

Important constraints.

## Current Decisions

Current assumptions and decisions.

## Terms We Use

Preferred terminology.

## Terms We Avoid

Terms that should not be used.

## Files / Links

Relevant files, links, or references.

## Open Questions

Known ambiguities or unresolved questions.
```

---

## Agent Spec Template

```markdown
# agent.function.v1

## Mission

The agent's core mission.

## Responsibilities

- Responsibility 1
- Responsibility 2
- Responsibility 3

## Inputs Needed

- Input 1
- Input 2
- Input 3

## Tools Needed

- Web research
- File reading
- Spreadsheet editing
- Calendar
- Email
- Slack
- Other

## Operating Rules

- Rule 1
- Rule 2
- Rule 3

## Output Format

The agent's standard output format.

## Platform Notes

### ChatGPT

Implementation notes for ChatGPT.

### Claude

Implementation notes for Claude.

### Other Platforms

Implementation notes for other platforms.

## Safety / Approval Rules

Actions that require manual confirmation.

## Version History

- v1: Initial version
```

---

## Workflow Template

```markdown
# workflow.process-name.v1

## Purpose

What this workflow does.

## Inputs

Required inputs.

## Steps

### Step 1: Research

Run:

```text
prompt.research.topic-map.v1
```

### Step 2: Strategy

Run:

```text
prompt.strategy.angle-selection.v1
```

### Step 3: Draft

Run:

```text
prompt.writing.draft.v1
```

### Step 4: Review

Run:

```text
prompt.editing.review.v1
```

## Outputs

Expected final outputs.

## Quality Checks

Required checks before finalizing.

## Notes

Operational notes.
```

---

## Handoff Packet Template

Use this when moving work from ChatGPT to Claude, from Claude to ChatGPT, or from one agent/tool to another.

```markdown
# AI Handoff Packet

## Goal

The final objective.

## Current State

What has already been done.

## Key Decisions

Decisions already made.

## Important Context

Context the next AI tool must know.

## Source Output

Previous output or summarized source material.

## What I Need From You

The exact next task.

## Constraints

Limitations, rules, or requirements.

## Desired Output Format

The expected output structure.
```

---

## Decision Log Template

```markdown
# decision.YYYY-MM-DD.topic

## Decision

The final decision.

## Context

The situation that led to this decision.

## Options Considered

### Option 1

Description.

### Option 2

Description.

### Option 3

Description.

## Why This Decision

Reason for choosing this option.

## Rejected Alternatives

Alternatives that were rejected and why.

## Implications

How this decision affects future work.

## Review Date

When this decision should be reviewed again.
```

---

## Standard Workflow

### 1. Do the work inside an AI tool

Use ChatGPT, Claude, Gemini, or an agent as the execution environment.

### 2. Do not save the raw chat

Raw chat is usually full of noise.

### 3. Extract the reusable assets

At the end of an important chat, use this prompt:

```text
Extract only the reusable assets from this conversation:

1. Prompts
2. Context packs
3. Agent specs
4. Workflow steps
5. Decisions
6. Output templates
7. Open questions

Return the result in Markdown.
Remove duplicate, conversational, low-value, and one-off content.
```

### 4. Save only the cleaned output

Store the distilled assets in the correct directory.

### 5. Commit the changes

```bash
git add .
git commit -m "update ai workspace assets"
git push
```

---

## Prompt for Converting a Chat into Repository Files

Use this at the end of a valuable AI session:

```text
Convert this conversation into files for my ai-workspace repository.

Return the output exactly in this structure:

## File: prompts/[domain]/[name].v1.md
[content]

## File: contexts/[project]/[name].v1.md
[content]

## File: agents/[platform-or-portable]/[name].v1.md
[content]

## File: workflows/[domain]/[name].v1.md
[content]

## File: decisions/YYYY/YYYY-MM-DD-[topic].md
[content]

Only generate files that are genuinely reusable.
Remove raw chat, commentary, introductions, and low-value content.
```

---

## Prompt for Creating an AI Handoff Packet

Use this when transferring work between AI tools:

```text
Create an AI Handoff Packet from the information below.

Goal:
[goal]

Current state:
[current state]

Key decisions:
[key decisions]

Previous output:
[source output]

Next task:
[next task]

Constraints:
[constraints]

Desired output format:
[desired output format]

Return the result in Markdown.
```

---

## Storage Decision Rule

```text
Will this be reused?
No → do not save it

Is only one part valuable?
Yes → extract only that part

Does it affect future decisions or workflows?
Yes → save it

Does it need version control?
Yes → Git

Is it only a final file?
Yes → outputs or file storage, not necessarily Git

Is it still raw or unclear?
Yes → inbox
```

---

## Commit Guidelines

For general updates:

```bash
git commit -m "update ai workspace assets"
```

For a new prompt:

```bash
git commit -m "add market research prompt v1"
```

For a new context pack:

```bash
git commit -m "add product context pack"
```

For a new workflow:

```bash
git commit -m "add blog production workflow"
```

For an important decision:

```bash
git commit -m "record pricing model decision"
```

---

## Review Cadence

### Daily or After an Important Session

- Extract important assets
- Update relevant files
- Commit changes

### Weekly

- Clean `inbox/`
- Merge duplicate prompts
- Remove low-value files
- Update stale context packs
- Move important decisions into `decisions/`

### Monthly

- Review core prompts
- Update agent specs
- Clean recurring workflows
- Mark deprecated files clearly
- Archive unused assets

---

## Final Rule

Do not save chats.  
Save the value extracted from chats.

```text
Do not manage conversations.
Manage reusable knowledge assets.
```
