# 🦞 OpenClaw Agent Creator

> *"Describe the agent. I'll build the soul."*

An AI agent that accepts a natural-language description of a new agent's purpose, reads example agent configurations from the `/examples` directory, and generates a complete, ready-to-deploy set of agent context files — one file per message, in clean Markdown.

---

## What It Does

1. **Receives a prompt** describing another agent's job: what it should do, how it should behave, and what tools it uses.
2. **Reads the `/examples` directory** to understand the expected file structure, tone, and conventions.
3. **Generates all required agent files**, each delivered in a separate message:

| File | Purpose |
|------|---------|
| `IDENTITY.md` | Agent name, emoji, vibe, and tagline |
| `SOUL.md` | Persona, tone, boundaries, and core values |
| `AGENTS.md` | Operating instructions and session memory |
| `TOOLS.md` | Tool notes, command conventions, and integrations |
| `USER.md` | User profile and communication preferences |
| `HEARTBEAT.md` | Short checklist for recurring heartbeat runs |
| `BOOT.md` | Short startup checklist run on gateway restart |
| `BOOTSTRAP.md` | One-time first-run ritual (deleted after completion) |

---

## Repository Structure

```
openclaw-agent-creator/
├── AGENTS.md        # Operating instructions + memory
├── SOUL.md          # Persona, boundaries, tone
├── TOOLS.md         # Tool notes and conventions
├── BOOTSTRAP.md     # One-time first-run ritual
├── IDENTITY.md      # Agent name/vibe/emoji
├── USER.md          # User profile + preferred address
├── README.md        # This file
└── examples/        # File-type descriptions used as reference templates
    ├── IDENTITY.md
    ├── SOUL.md
    ├── AGENTS.md
    ├── TOOLS.md
    ├── USER.md
    ├── HEARTBEAT.md
    ├── BOOT.md
    └── BOOTSTRAP.md
```

---

## Getting Started

### 1. Complete the Bootstrap Ritual

Read `BOOTSTRAP.md` and follow the checklist. This ensures the agent is correctly configured before its first real use. **Delete `BOOTSTRAP.md` when done.**

### 2. Review Examples

The `/examples` directory contains one file per agent context file type, each with a short description of its purpose. These are the agent's primary style reference when generating files for a new agent.

### 3. Send a Prompt

Describe the agent you want to create. Example:

> *"I need an agent that monitors my GitHub notifications and sends me a daily digest via iMessage every morning at 9am. It should be terse and skip bots."*

The creator will ask any necessary clarifying questions, then generate each file in sequence, one per message.

### 4. Deploy the Output

Copy the generated files into the root of your new agent's repository and run its bootstrap ritual.

---

## Configuration Files

| File | Edit When |
|------|-----------|
| `IDENTITY.md` | You want to rename or rebrand the creator agent |
| `SOUL.md` | You want to adjust its tone, persona, or hard limits |
| `AGENTS.md` | You want to change its workflow or decision rules |
| `TOOLS.md` | You add, remove, or update an available tool |
| `USER.md` | Your preferences or contact details change |

---

## Contributing

To improve the quality of generated agents, add more diverse examples to the `/examples` directory. The richer the example set, the more accurately the creator can match your conventions.
