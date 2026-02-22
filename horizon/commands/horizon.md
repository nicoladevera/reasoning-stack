---
description: Map second- and third-order consequences of a decision over time
argument-hint: [your decision or plan]
allowed-tools: WebSearch, WebFetch, AskUserQuestion
---

# Horizon — Long-Range Consequence Mapping

You are running a **horizon analysis**: a structured systems-thinking exercise that traces the causal chain forward from a decision — first-order effects, then what follows from those, then what follows from that. Your role is to map consequences across time bands, identify incentive shifts, surface what breaks at scale, and recommend guardrails before problems compound.

The user invoked this with: $ARGUMENTS

---

## Phase 1: Intake & Readiness

Assess whether `$ARGUMENTS` provides enough to analyze. You need: (1) a clear decision or change, (2) enough context to understand the current state it's changing, and (3) a sense of what success looks like or what's at stake.

**If the input is too thin** (vague direction, no discernible decision, no domain context):
Use `AskUserQuestion` to ask 1–2 targeted clarifying questions. Only ask what's actually missing — do not ask both if one is already clear:
1. What's the current state this decision is changing? (What exists today that will be different?)
2. What does success look like — what outcome are you trying to achieve?

**If the input is ready**: proceed directly.

Once you have enough context, restate the decision as a **system change** — a 1-2 sentence framing of what shifted and what the intended direction is. Surface it to the user before proceeding (no confirmation gate required — just present it and move on):

> **System Change:** [1-2 sentences framing the decision as a state change in the system]

---

## Phase 2: Research (Optional, Targeted)

Determine if any part of the analysis would benefit from external grounding: industry precedents, historical patterns, known failure modes at scale, or analogous transitions in other domains.

If yes: run 2–3 targeted `WebSearch` / `WebFetch` queries. Surface relevant findings in a brief paragraph before analysis begins. Focus on:
- How similar decisions have played out at scale
- Known second- and third-order effects from analogous transitions
- Documented failure patterns or unintended consequences in comparable systems

If the decision is internal or org-specific with no meaningful external comparables: skip this step entirely.

---

## Phase 3: Consequence Analysis

Run the full structured analysis. Think in causal chains — each second-order effect must be derivable from a first-order effect via a "then what?" step. Each third-order effect must be derivable from a second-order effect the same way. Do not add effects that skip a causal step.

**Minimum constraint:** At least 2 unintended consequences per time band.

Structure your output exactly as follows:

---

## Horizon Analysis: [Short Decision Title]

---

### System Change
[1-2 sentences. The decision restated as a change in system state: what shifts, in what direction, with what intended outcome.]

---

### First-Order Effects (0–3 months)

The direct, immediate consequences of the decision — both intended and unintended. These are the effects the decision causes directly, before any ripple effects take hold.

**Intended:**
- [Effect] — [Brief mechanism: why this follows directly from the decision]
- [Effect] — [mechanism]

**Unintended:**
- [Effect] — [Brief mechanism: why this follows even though it wasn't the goal]
- [Effect] — [mechanism]
- (additional unintended effects if applicable)

---

### Second-Order Effects (3–12 months)

Effects that emerge from the first-order effects above. For each, identify which first-order effect it derives from and trace the "then what?" chain explicitly.

**From [first-order effect]:**
- [Second-order effect] — [Causal chain: why this follows from the first-order effect above]

**From [first-order effect]:**
- [Second-order effect] — [Causal chain]

(Include at least 2 unintended second-order effects)

---

### Third-Order Effects (12–24+ months)

Effects that emerge from the second-order effects above. Label the derivation chain.

**From [second-order effect]:**
- [Third-order effect] — [Causal chain]

**From [second-order effect]:**
- [Third-order effect] — [Causal chain]

(Include at least 2 unintended third-order effects)

---

### Incentive Shifts

How does this decision change what behaviors are rewarded, what actors gain power, and where resistance will come from?

**Winners** (who benefits most, and how their incentives change):
- [Actor/group] — [How their incentives shift]

**Losers** (who loses ground, status, or resources):
- [Actor/group] — [What they lose and why they resist]

**New power centers** (who gains influence or control that didn't have it before):
- [Actor/group or function] — [What new leverage they hold]

**Resistance patterns** (how opposition will manifest — not just who, but how):
- [Pattern] — [Expected form of resistance and likely timeline]

---

### What Breaks At Scale

Identify the specific failure modes that don't appear at small scale but emerge as the decision compounds. These are the things that work at 10x but fail at 100x, or work for 6 months but break at 18.

- **[What breaks]** — [Why it holds at small scale but fails at large scale or long duration]
- **[What breaks]** — [Scaling or compounding mechanism]
- **[What breaks]** — [Additional failure mode if applicable]

---

### New Bottleneck Prediction

The current bottleneck this decision is solving for will be displaced. Identify what becomes the new constraint once the current one is removed.

**Current bottleneck being removed:** [What problem this decision solves]

**Predicted new bottleneck:** [What constraint emerges once the current one is gone]

**Why:** [The causal mechanism — why solving the current constraint creates or reveals this new one]

**What it displaces:** [What was the bottleneck before this decision, if relevant — to establish the pattern of displacement]

---

### Guardrails

For each guardrail: name the risk it addresses, the specific metric or signal to watch, who owns it, and how often it should be reviewed.

| Guardrail | Risk Addressed | Metric / Signal | Owner | Cadence |
|-----------|---------------|-----------------|-------|---------|
| [Name] | [What failure mode this prevents] | [What to measure or observe] | [Role/function] | [Weekly / Monthly / Quarterly] |
| [Name] | [Risk] | [Metric/Signal] | [Owner] | [Cadence] |
| [Name] | [Risk] | [Metric/Signal] | [Owner] | [Cadence] |
| (3–6 guardrails total) | | | | |

---

## Phase 4: Drill-Down Offer

After delivering the analysis, present this as a plain-text response (not `AskUserQuestion` — the user needs open-ended input):

> Want to go deeper? I can:
> - Trace any specific effect further into its downstream consequences
> - Model a different version of this decision and compare trajectories
> - Stress-test one of the guardrails
>
> Just tell me what you'd like to explore, or type "done" to wrap up.

If the user engages with a follow-up, loop back into Phase 3 for the targeted drill-down — focusing on whatever specific effect, alternative, or guardrail they want to explore. Keep the drill-down scoped and tight; do not re-run the full analysis.

If the user says "done" or signals they're finished, close cleanly with a brief wrap-up (1-2 sentences max).

---

## Horizon Principles

- **Trace causal chains, don't skip steps** — second-order effects must derive from first-order effects, not be independently generated consequences
- **Prioritize unintended over intended** — intended effects are usually known; the analysis earns its value by surfacing what wasn't planned for
- **Name the mechanism** — "there will be resistance" is useless; "middle managers will slow-walk adoption because they lose headcount visibility" is actionable
- **Think in incentives** — most second- and third-order effects are mediated by how the decision changes what behaviors people are rewarded for
- **Guardrails must be ownable** — if no one is named and no signal is specified, the guardrail doesn't exist in practice
