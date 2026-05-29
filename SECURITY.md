# Security Policy

## Threat surface

**SpecLock** is a documentation-only plugin. Its attack surface is intentionally minimal:

- **No executable code** — no scripts, binaries, or build steps.
- **No MCP servers** — nothing runs as a server or background process.
- **No hooks** — it does not register pre/post hooks that execute commands.
- **No network access** — it makes zero outbound requests.
- **No credentials or secrets** — it neither reads nor stores any.

It contains only Markdown: one skill definition, one command, and four reference templates.
Everything it can do is auditable by reading the files in this repository.

## What it can write

When the skill is active, Claude writes Markdown files (`CLAUDE_LOG.md`, specs, ADRs) into
your repository's working tree, following the templates. It writes nowhere else and reads
only its own bundled reference files.

## Reporting a vulnerability

If you find a security issue (for example, prompt content that could be abused to mislead
Claude), please report it privately via GitHub's **Security advisories** on this repository,
or open an issue if it is low risk. We aim to respond within a few business days.

## Supported versions

The latest released version (see [CHANGELOG.md](CHANGELOG.md)) is supported. Fixes are
shipped as new versions; older versions are not patched in place.
