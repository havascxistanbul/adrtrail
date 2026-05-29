# ADRTrail

A Claude Code plugin that installs a **spec-first engineering discipline**: decide before you build, and write down why.

It prevents the most common failure mode in AI-assisted engineering — jumping straight to code, accumulating undocumented decisions, and producing a system nobody can reason about later. The plugin front-loads the thinking and leaves a durable, auditable trail.

## What it does

The skill enforces three artifacts, produced in a fixed order:

1. **Spec** — what you are building and the boundaries, locked before any code.
2. **ADRs** — one Architecture Decision Record per significant choice, including the alternatives rejected and the downsides accepted.
3. **CLAUDE_LOG** — an append-only, chronological ledger of decisions and actions across the session.

The ordering is the whole point: **Spec lock → ADR per decision → CLAUDE_LOG throughout.**

## Installation

### From a marketplace

Add the marketplace, then install:

```
/plugin marketplace add havascxistanbul/adrtrail
/plugin install adrtrail@adrtrail
```

### Local development / testing

```
claude --plugin-dir ./adrtrail
```

## Usage

Once installed, the skill triggers automatically when you start a feature, service, or refactor, or when you mention specs, ADRs, architecture decisions, or decision logs. You can also invoke it explicitly:

> "Let's spec-first this. I want to build a notification service."

Claude will lock a spec with you before writing code, record an ADR for each significant decision, and keep a `CLAUDE_LOG.md` at your repo root.

## Output layout

```
<repo-root>/
├── CLAUDE_LOG.md              # append-only session ledger
└── docs/
    ├── specs/
    │   └── <feature>-spec.md
    └── adr/
        ├── ADR-0001-<slug>.md
        └── ADR-0002-<slug>.md
```

If your repo already has a docs convention, the skill follows yours instead of imposing this one.

## Contents

| Path | Purpose |
|------|---------|
| `commands/spec-first.md` | `/spec-first` slash command to invoke the discipline |
| `skills/adrtrail/SKILL.md` | The discipline and workflow |
| `skills/adrtrail/references/spec-template.md` | Spec template |
| `skills/adrtrail/references/adr-template.md` | ADR template |
| `skills/adrtrail/references/claude-log-format.md` | CLAUDE_LOG format and rules |
| `skills/adrtrail/references/examples.md` | Worked end-to-end example |

## Safety

This plugin is **pure documentation discipline**. It contains no MCP servers, no hooks, no executable scripts, and makes no network calls. It only reads its own templates and writes Markdown files into your repository. Review the contents before installing — everything it can do is in the files listed above.

See [PRIVACY.md](PRIVACY.md) (no data collected, no telemetry) and [SECURITY.md](SECURITY.md) (threat surface and reporting).

## License

MIT — see [LICENSE](LICENSE).
