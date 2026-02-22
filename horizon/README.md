# /horizon — Long-Range Consequence Mapping

Map second- and third-order consequences of a decision over time. Horizon traces causal chains forward, identifies incentive shifts, predicts what breaks at scale, and recommends guardrails before problems compound.

---

## Install

```bash
# From the repo root
./install.sh horizon

# Or manually
cp horizon/commands/horizon.md ~/.claude/commands/horizon.md
```

---

## Usage

```
/horizon [your decision or plan]
```

**Examples:**

```
/horizon If we move to async-first engineering culture, what happens?
/horizon We're planning to consolidate our three product lines into one platform
/horizon Switching from per-seat to usage-based pricing for our enterprise tier
/horizon Mandate that all internal services expose a public API within 12 months
```

If your input is thin or vague, the command will ask 1–2 clarifying questions before proceeding.

---

## How It Works

### Phase 1: Intake & Readiness

The command assesses whether your input has enough context for meaningful analysis. If not, it asks 1–2 targeted questions (max) to establish: what the current state is, what's changing, and what success looks like. Once it has enough, it restates the decision as a **system change** — a 1-2 sentence framing of what shifted — and surfaces it before proceeding.

### Phase 2: Optional Research

For decisions with useful external analogues, the command runs 2–3 targeted web searches to surface real-world precedents, known failure modes, and patterns from analogous transitions. Skipped for purely internal or org-specific decisions with no meaningful external comparables.

### Phase 3: Consequence Analysis

A full structured analysis covering:

- **System Change** — the decision restated as a state change in the system
- **First-Order Effects (0–3 months)** — direct consequences, intended and unintended
- **Second-Order Effects (3–12 months)** — what follows from first-order effects via explicit "then what?" chains
- **Third-Order Effects (12–24+ months)** — what follows from second-order effects
- **Incentive Shifts** — winners, losers, new power centers, and resistance patterns
- **What Breaks At Scale** — failure modes that don't appear small but emerge as the decision compounds
- **New Bottleneck Prediction** — what constraint replaces the one this decision removes
- **Guardrails** — with metric/signal, owner, and cadence for each

**Minimum constraint:** At least 2 unintended consequences per time band.

### Phase 4: Drill-Down

After delivering the analysis, the command offers to go deeper on any specific effect, model an alternative version of the decision, or stress-test a guardrail. Drill-downs loop back into targeted analysis — they don't re-run the full output.

---

## Output Format

```
## Horizon Analysis: [Short Decision Title]

### System Change
### First-Order Effects (0–3 months)
### Second-Order Effects (3–12 months)
### Third-Order Effects (12–24+ months)
### Incentive Shifts
### What Breaks At Scale
### New Bottleneck Prediction
### Guardrails
```

---

## When to Use It

Use `/horizon` when you:

- Are about to commit to a structural decision with long-range implications
- Need to anticipate second- and third-order effects before they materialize
- Want to understand how a change shifts incentives across the system
- Are trying to identify what breaks at scale before you get there
- Want to design guardrails into a plan from the start, not after problems appear

---

## How It Relates to Other Commands

- Use `/premortem` when you want to stress-test a specific idea by assuming it already failed and working backward
- Use `/forum` when you want multi-perspective debate to weigh pros and cons across expert lenses
- Use `/horizon` when you want to trace causal chains *forward* across time — less about "is this a good idea?" and more about "what does this set in motion?"

---

## Requirements

- Claude Code (standard installation)
- No multi-agent tools required — single-agent, runs entirely in one session
