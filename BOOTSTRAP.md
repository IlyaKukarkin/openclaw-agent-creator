# 🚀 BOOTSTRAP.md — First-Run Ritual

> ⚠️ **This file is intended to be deleted after the first-run ritual is complete.**

---

## Purpose

This file guides the very first interaction between the user and the OpenClaw Agent Creator. It ensures the agent is properly oriented before handling any real generation requests.

---

## First-Run Checklist

Complete the following steps **in order** during the first session:

### 1. Confirm Identity
Read `IDENTITY.md` and confirm the agent's name, emoji, and tagline are correct. If any details need adjusting, update `IDENTITY.md` now.

### 2. Review Soul & Boundaries
Read `SOUL.md`. Confirm that the persona, tone, and boundaries match the intended use of this agent. Adjust if needed.

### 3. Update User Profile
Open `USER.md` and fill in:
- Your name or preferred address
- Any preferences the agent should know about (communication style, output format, etc.)
- Timezone (if relevant for scheduled or time-sensitive tasks)

### 4. Populate Tool Notes
Open `TOOLS.md` and verify that all tools you intend to use are documented. Add any custom tools or shortcuts specific to your environment.

### 5. Review Examples Directory
Check the `/examples` directory. If it is empty, add at least one sample agent context file set so the agent has a reference for future generation tasks. Even a minimal example helps calibrate output quality.

### 6. Test with a Simple Prompt
Send the agent a short test prompt such as:
> *"Create an agent that reminds me to drink water every hour via iMessage."*

Confirm that:
- The agent asks clarifying questions if the prompt is insufficient.
- The agent generates each file in a separate message.
- The output matches the style of files in `/examples`.

### 7. Delete This File
Once all steps above are complete, delete `BOOTSTRAP.md` from the repository. Its presence on future runs would cause confusion.

---

## Troubleshooting

| Issue | Resolution |
|-------|-----------|
| Agent generates all files in one message | Remind it: *"Generate each file in a separate message."* |
| Output style doesn't match examples | Check that `/examples` is populated and re-run with `--reload-examples`. |
| Agent asks too many clarifying questions | Add more detail to `USER.md` about your preferences. |
| Agent skips the examples lookup | Explicitly say: *"Check `/examples` before generating."* |

---

*Delete this file once the bootstrap ritual is complete.*
