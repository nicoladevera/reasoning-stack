# /forum — Council of Agents

Convene a multi-agent council to pressure-test any idea, decision, or strategy through structured debate. The forum guides your idea through 4 phases, ending with a clear written recommendation — not a hedge.

---

## Install

```bash
# From the repo root
./install.sh forum

# Or manually
cp forum/commands/forum.md ~/.claude/commands/forum.md
```

---

## Usage

```
/forum [your idea or question]
```

**Examples:**

```
/forum Should we rewrite our monolith as microservices?
/forum I want to launch a paid tier for my open-source tool
/forum Is this the right time to raise a seed round?
```

If your idea is vague, the facilitator will ask up to 3 clarifying questions before proceeding.

---

## How It Works

### Phase 1: Intake & Readiness

The facilitator assesses whether your idea has enough context for meaningful debate. If not, it asks targeted clarifying questions. Once it understands the idea, it presents a **crystallized brief** — a 1-3 sentence distillation of your core question — and asks you to confirm it before anything else happens.

After brief confirmation, the facilitator proposes a **council composition**: the expert roles most relevant to your specific idea. You approve (or adjust) the council before anyone is spawned.

### Phase 2: Open Questions & Unknowns

The council is spawned. Before any debate begins, each member independently flags what information is missing, ambiguous, or unvalidated. These questions are consolidated and surfaced to you. What you can answer gets incorporated; what you can't becomes a **declared assumption** the council works under.

If factual gaps remain, the facilitator runs targeted web research (2-4 queries max) before opening the debate.

### Phase 3: Council Discussion

Three structured rounds:

1. **Independent positions** — each agent gives their initial assessment without seeing others' views (prevents anchoring)
2. **Open debate** — all positions are shared; agents respond to each other's views
3. **Final recommendation** (if needed) — each agent states their definitive call and the single most important reason for it

The facilitator summarizes each round as it completes so you can follow along.

### Phase 4: Output Artifact

A structured written output covering:

- Core topic and context
- Declared assumptions
- Supporting and dissenting views (by role)
- Key risks
- A clear recommendation (not "it depends")
- Consensus signal: Unanimous / Majority (N–N) / Contested
- Immediate next steps

---

## Output Format

```
## Forum Output

**Core Topic**
*[Short title phrase]*
[2-3 sentences describing what's being discussed and why it matters]

**Declared Assumptions**
- [assumption 1]
- [assumption 2]

**Supporting Views**
- **[Agent Role]:** [Key argument in 1-2 sentences]

**Dissenting Views**
- **[Agent Role]:** [Key objection in 1-2 sentences]

**Risks**
- [Risk 1]
- [Risk 2]

**Recommendation:** [Clear directive]
**Rationale:** [Why this recommendation, given the debate]
**Consensus Signal:** Unanimous / Majority (N–N) / Contested

**Immediate Next Steps**
1. [Concrete action]
2. [Concrete action]
```

---

## Council Composition

The facilitator infers council roles from the domain and nature of your idea. For a product strategy question, you might get a Product Strategist, a Market Analyst, and a Customer Experience Researcher. For a technical architecture decision, an Engineer, a Security Architect, and an Engineering Manager.

You review and approve the proposed council before anyone is spawned. You can swap roles, add members, or remove perspectives that aren't relevant.

Agents identify themselves by role title only — not by invented names — to keep the focus on the perspective, not the persona.

---

## Requirements

- Claude Code with multi-agent support (`TeamCreate`, `SendMessage`, `Task` tools)
- Available in standard Claude Code installations
