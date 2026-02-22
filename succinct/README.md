# /succinct — Compression to Executive Artifact

Your thinking is correct but too large to land. `/succinct` compresses a messy, expansive idea into a tight executive-ready artifact: one thesis, three load-bearing pillars, one tradeoff, one metric, one decision ask.

---

## Install

```bash
# From the repo root
./install.sh succinct

# Or manually
cp succinct/commands/succinct.md ~/.claude/commands/succinct.md
```

---

## Usage

```
/succinct [your idea, proposal, or strategy]
```

**Examples:**

```
/succinct We should build a native mobile app instead of continuing to invest in our PWA because enterprise customers keep telling us they won't buy without an App Store presence
/succinct Our platform team should own the data pipeline infrastructure instead of having each product team build their own
/succinct We need to deprecate our v1 API in the next two quarters even though 15% of customers are still on it
```

If your input is too vague, the command will ask up to 3 clarifying questions before proceeding.

---

## How It Works

### Phase 1: Intake & Readiness

The command assesses whether your idea has enough context for meaningful compression. If not, it asks targeted clarifying questions (max 3) — what the idea is, who the audience is, and what outcome you need. Once it has enough, it proceeds without confirmation.

### Phase 2: Compression (Silent)

The agent runs the compression process internally without showing its work. It identifies the single thesis, selects the three most load-bearing pillars (discarding elaboration and decoration), names the real tradeoff being made, picks the one governing metric, and forms a concrete decision ask. Any inferences made from context are flagged as assumptions.

### Phase 3: Output

A structured executive artifact ready to paste into a slide, a doc, or a conversation.

---

## Output Format

```
## Succinct: [Short Title]

### Thesis
One sentence. The single claim the whole thing rests on.

### Pillars
1. [Pillar 1] — Why this is load-bearing.
2. [Pillar 2] — Why this is load-bearing.
3. [Pillar 3] — Why this is load-bearing.

### Key Tradeoff
We are choosing [X] over [Y]. [Why that's the right call.]

### Success Metric
[Metric name]: [Specific, measurable target and timeframe.]

### Decision Ask
[Action verb] [specific commitment].

### Assumptions
[Only present if the agent inferred context you didn't provide.]

### One-Slide Version
> [Thesis]
> Because: [Pillar 1] / [Pillar 2] / [Pillar 3]
> Tradeoff: [X] over [Y]
> We'll know it's working when: [Metric]
> We need you to: [Decision ask]
```

---

## When to Use It

Use `/succinct` when you:

- Have a proposal that's correct but too long to land in an exec conversation
- Need to prepare a strategy doc and want to force-rank what's actually load-bearing
- Are about to present a decision and want to know what you're really asking for
- Have been thinking about something for weeks and need to compress it to a single page

It complements `/premortem` (stress-test a decision) and `/forum` (debate across perspectives) — use `/succinct` when the thinking is done and the problem is communication, not correctness.

---

## Requirements

- Claude Code (standard installation)
- No web research or multi-agent coordination required — single-agent, runs entirely in one session
