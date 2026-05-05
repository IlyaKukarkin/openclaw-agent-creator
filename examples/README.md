# Examples

This directory contains sample agent context file-sets that the **OpenClaw Agent Creator** uses as reference templates when generating new agents.

## How to Use

Each subdirectory (or group of files) here represents a complete agent configuration. When generating a new agent, the creator reads all files in this directory to understand:

- The expected structure and ordering of sections
- Tone and persona conventions
- Naming and formatting patterns

## Adding Examples

To add an example:

1. Create a subdirectory named after the agent (e.g., `examples/water-reminder-agent/`).
2. Place the full set of agent files inside it: `IDENTITY.md`, `SOUL.md`, `AGENTS.md`, `TOOLS.md`, `BOOTSTRAP.md`, `USER.md`.
3. Commit the files. The creator will pick them up automatically on the next run.

> **Note:** At least one example should be present before using the creator in production. An empty `/examples` directory will cause the agent to fall back to its built-in conventions.
