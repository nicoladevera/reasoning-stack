# /conviction — Epistemic Belief Audit

Turn a belief, claim, or decision into a structured epistemic audit: assumptions mapped, evidence weighed, confidence scored, and the cheapest falsifying test designed. For when you're operating on partial information and need to know how much to trust what you think you know.

---

## Install

```bash
# From the repo root
./install.sh conviction

# Or manually
cp conviction/commands/conviction.md ~/.claude/commands/conviction.md
```

---

## Usage

```
/conviction [your belief, claim, or decision]
```

**Examples:**

```
/conviction My sense is Claude Code is more performant than Claude-in-Copilot
/conviction We should build on top of this vendor's API rather than building in-house
/conviction Our biggest retention risk is onboarding friction, not product gaps
/conviction The market for this product is larger in enterprise than SMB
```

If your belief is vague or lacks context, the command will ask up to 3 clarifying questions before proceeding.

---

## How It Works

### Phase 1: Intake & Readiness

The command assesses whether your input contains a clear, evaluable belief or claim. If not, it asks targeted clarifying questions (max 3). Once it has enough context, it restates the claim in **falsifiable form** — a precise statement that could, in principle, be shown to be true or false — and surfaces it before moving on.

### Phase 2: Optional Research

For claims where external data would meaningfully ground the analysis — base rates, published benchmarks, analogous comparisons — the command runs 2–3 targeted web searches and surfaces relevant findings before the audit. Skipped for purely internal or subjective beliefs with no useful external comparables.

### Phase 3: Conviction Audit

A full structured epistemic audit covering:

- **Claim (falsifiable)** — the belief restated precisely
- **Assumptions** — core (load-bearing) vs. supporting
- **Evidence** — for, against, and unknown/needs data
- **Confidence Score** — score out of 100 with 2–4 bullet rationale
- **What Would Change My Mind** — specific disconfirmation criteria
- **Tests** — 48-hour and 2-week experiments with pass/fail rules
- **Decision Rule** — when to act now vs. wait for more data

### Phase 4: Drill-Down Offer

After the audit, the command offers to go deeper: revisit a specific assumption, steelman the opposing view, or design an additional test for the hardest-to-resolve unknown.

---

## Output Format

```
## Conviction Audit: [Short Claim Title]

## Claim (falsifiable)
[Precise, falsifiable restatement]

## Assumptions
  ### Core (must be true)
  ### Supporting

## Evidence
  ### For
  ### Against
  ### Unknown / needs data

## Confidence Score
  - Score: __/100
  - Rationale (2–4 bullets)

## What Would Change My Mind

## Tests
  ### 48-Hour Test
  | Test | How to Run | Pass | Fail |

  ### 2-Week Test
  | Test | How to Run | Pass | Fail |

## Decision Rule
  - Act now if:
  - Wait if:
```

---

## When to Use It

Use `/conviction` when you:

- Have a strong intuition or working assumption you've never formally examined
- Are about to make a decision based on a belief that hasn't been tested
- Want to know how much your confidence is actually warranted
- Need to communicate a position and want to know where it's weakest

**Contrast with other commands:**

- Use `/premortem` when you want to stress-test a *decision* by assuming it fails and working backward
- Use `/forum` when you want to pressure-test an *idea* through multi-perspective debate
- Use `/conviction` when you want to audit a *belief* — map what you actually know, what you're assuming, and what would change your mind

---

## Requirements

- Claude Code (standard installation)
- No multi-agent tools required — single-agent, runs entirely in one session
