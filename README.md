# Claude QMS

A Quality Management System for AI-assisted software development. Claude QMS provides document control, change management, and traceability for projects where AI agents collaborate with human leads.

## Quick Start

```bash
# Clone with submodules
git clone --recurse-submodules https://github.com/whharris917/claude-qms.git
cd claude-qms

# Initialize QMS infrastructure
cd qms-cli
python qms.py init --yes

# Verify it works
cd ..
python qms-cli/qms.py --user claude create CR --title "My First Change"
python qms-cli/qms.py --user claude inbox
```

## What Gets Created

Running `qms init` creates the following in this project root:

| Artifact | Purpose |
|----------|---------|
| `qms.config.json` | Project configuration |
| `QMS/` | Document storage (CRs, INVs, Templates) |
| `QMS/.meta/` | Document metadata |
| `QMS/.audit/` | Audit trails |
| `.claude/users/` | Workspaces for lead, claude, qa, tu |
| `.claude/agents/` | Agent definitions (qa.md, tu.md) |
| `.claude/hooks/` | Write guard hook |
| `CLAUDE.md` | Orchestrator instructions |

## Project Structure

```
claude-qms/
├── .claude-qms          # Marker file (tells qms init where to unpack)
├── .gitmodules
├── .gitignore
├── README.md
├── Quality-Manual/      # Submodule: QMS operational documentation
│   ├── QMS-Policy.md     # Core policy decisions
│   ├── START_HERE.md     # Decision tree for common workflows
│   ├── QMS-Glossary.md   # Term definitions
│   ├── guides/           # Operational guides
│   └── types/            # Document type references
└── qms-cli/             # Submodule: QMS CLI tooling
    ├── qms.py            # Main CLI entry point
    ├── commands/          # Command implementations
    ├── seed/              # Templates, agents, hooks seeded by init
    └── docs/              # Software documentation
```

## Documentation

After cloning, documentation is available at:

- **Quality Manual:** `Quality-Manual/START_HERE.md` — How to operate the QMS
- **QMS Policy:** `Quality-Manual/QMS-Policy.md` — Core policy decisions
- **Getting Started:** `qms-cli/docs/getting-started.md` — First-time CLI setup
- **CLI Reference:** `qms-cli/docs/cli-reference.md` — Every command and flag

## License

See individual files for license information.
