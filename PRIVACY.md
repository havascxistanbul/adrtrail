# Privacy Policy

**ADRTrail** is a pure-documentation Claude Code plugin. It changes how Claude
*works* (lock a spec, write ADRs, keep a decision log) — it does not collect, transmit,
or process any user data.

## What this plugin does

- Provides a skill (`adrtrail`), a slash command (`/spec-first`), and four Markdown
  reference templates that guide Claude's behavior.
- When triggered, Claude reads those templates and writes Markdown files (`CLAUDE_LOG.md`,
  spec docs, ADRs) **into your own repository, on your machine**.

## What this plugin does NOT do

- ❌ No data collection. It records nothing about you, your code, or your usage.
- ❌ No telemetry or analytics. It phones home to no one.
- ❌ No network calls. It makes no outbound requests of any kind.
- ❌ No MCP servers, hooks, or executable scripts. It contains only Markdown.
- ❌ No third-party services. Nothing is shared with any party.

## Data it touches

The only data involved is the content **you and Claude create**: spec, ADR, and
CLAUDE_LOG Markdown files written into your repository. These files live entirely under
your control, in your working tree, and the plugin never reads them back out, copies them,
or sends them anywhere.

## Changes

Any change to this policy will be recorded in [CHANGELOG.md](CHANGELOG.md) and committed to
this repository.

## Contact

Questions about privacy: open an issue on the repository.
