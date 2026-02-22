# Custom Claude Code Commands

A collection of custom slash commands for [Claude Code](https://claude.ai/code). Each command is a structured prompt that extends Claude Code with specialized workflows.

---

## Prerequisites

- [Claude Code](https://claude.ai/code) installed and configured
- Commands that use multi-agent features require Claude Code with `TeamCreate`, `SendMessage`, and `Task` tool support (available in standard Claude Code installations)

---

## Installation

### Option 1: Install script

Clone the repo and run `install.sh`:

```bash
git clone https://github.com/nicoladevera/custom-commands.git
cd custom-commands

# Install all commands
./install.sh

# Install a specific command
./install.sh forum
```

### Option 2: Manual copy

Copy the command file directly to your Claude Code commands directory:

```bash
cp forum/commands/forum.md ~/.claude/commands/forum.md
```

Commands are available immediately — no restart required. Invoke them in Claude Code with `/command-name`.

---

## Command Index

| Command | Description | Install path |
|---------|-------------|--------------|
| [`/forum`](./forum/README.md) | Convene a council of agents to pressure-test an idea through structured debate | `~/.claude/commands/forum.md` |
| [`/premortem`](./premortem/README.md) | Assume your idea has already failed — work backward to find out why | `~/.claude/commands/premortem.md` |
| [`/horizon`](./horizon/README.md) | Map second- and third-order consequences of a decision over time | `~/.claude/commands/horizon.md` |

---

## Adding Your Own

Each command lives in its own directory:

```
command-name/
├── README.md              # Documentation
└── commands/
    └── command-name.md    # The prompt file Claude Code reads
```

The `.md` file supports Claude Code frontmatter (`description`, `argument-hint`, `allowed-tools`) and full markdown prompt content.
