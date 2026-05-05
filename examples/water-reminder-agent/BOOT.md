# 🥾 BOOT.md — Startup Checklist

> **File purpose:** Optional startup checklist run automatically on gateway restart (when internal hooks are enabled). Keep it short; use the message tool for outbound sends.

---

## Checklist

- [ ] Load configuration from `AGENTS.md` (recipient, interval, quiet hours, log path)
- [ ] Verify `imsg` is available and the host iMessage session is active
- [ ] Confirm log file path exists and is writable; create it if absent
- [ ] Check current time against quiet hours — suppress first send if inside quiet window
- [ ] Schedule first heartbeat tick at `INTERVAL_MINUTES` from now
- [ ] Log boot event: `{ "event": "boot", "status": "ok", "ts": "<now UTC>" }`
