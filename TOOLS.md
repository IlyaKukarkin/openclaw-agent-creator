# 🛠️ TOOLS.md — Tool Notes & Conventions

> **Maintained by:** User (IlyaKukarkin)
> **Purpose:** Document the tools, shortcuts, and conventions available to the OpenClaw Agent Creator and the agents it generates.

---

## Tool Index

### `imsg` — iMessage Integration
- **What it does:** Sends and receives iMessages programmatically.
- **Typical use:** Agents that notify the user via iMessage, or that accept commands sent as messages.
- **Convention:** Use `imsg send "<recipient>" "<message>"` syntax. Recipient can be a phone number or Apple ID email.
- **Notes:** Requires the host machine to have an active iMessage account. Not available in headless/server environments.

### `sag` — Shell Agent Gateway
- **What it does:** Provides a shell interface for spawning, communicating with, and terminating sub-agents.
- **Typical use:** Orchestrator agents that manage other agents or delegate sub-tasks.
- **Convention:** Use `sag run <agent-name> --prompt "<prompt>"` to invoke a sub-agent. Use `sag status <agent-id>` to check state.
- **Notes:** Sub-agents run asynchronously by default. Use `--sync` flag for blocking calls.

---

## General Conventions

### File Naming
- All agent context files use `UPPERCASE.md` naming (e.g., `AGENTS.md`, `SOUL.md`).
- Example files in `/examples` follow the same convention.

### Markdown Style
- Use ATX-style headers (`#`, `##`, `###`).
- Use fenced code blocks with language identifiers where applicable.
- Use tables for structured comparisons or indexes.
- Avoid raw HTML in Markdown files.

### Tone Markers
- Emoji are used at the start of top-level headers to add visual identity.
- Keep emoji usage tasteful — one per major section header, not inline spam.

### Version / Update Tracking
- Files that change over time should include an **Update Log** table at the bottom.

---

## Adding New Tools

To add a new tool entry, append a new `###` subsection to the **Tool Index** above with the following fields:
- **What it does**
- **Typical use**
- **Convention** (command syntax or API shape)
- **Notes** (caveats, environment requirements, known issues)
