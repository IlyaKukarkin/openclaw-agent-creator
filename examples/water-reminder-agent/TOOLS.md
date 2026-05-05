# 🛠️ TOOLS.md — Local Tool Conventions

> **File purpose:** Notes about your local tools and conventions. Does not control tool availability; it is only guidance.

---

## Tools Used by This Agent

### `imsg` — iMessage Integration
- **What it does:** Sends iMessages from the host machine.
- **Usage in this agent:** Delivers hydration reminders to the configured recipient.
- **Command convention:**
  ```
  imsg send "<recipient>" "<message>"
  ```
- **Return value:** Exit code `0` on success, non-zero on failure. Check stderr for error details.
- **Notes:**
  - Requires an active iMessage session on the host Mac.
  - `<recipient>` can be a phone number (`+1XXXXXXXXXX`) or an Apple ID email address.
  - Messages longer than 160 characters may be split; keep reminder text short.

---

## Conventions

### Logging
- Write one JSON line per event to `LOG_FILE` (defined in `AGENTS.md`).
- Schema:
  ```json
  { "ts": "2026-05-05T09:00:00Z", "event": "send", "status": "ok", "message": "..." }
  { "ts": "2026-05-05T09:00:01Z", "event": "send", "status": "failed", "error": "..." }
  ```
- Never truncate or rotate the log automatically; the user manages log lifecycle.

### Timezone Handling
- All timestamps in the log are UTC (ISO 8601).
- Quiet-hour comparisons use the host machine's local time.
