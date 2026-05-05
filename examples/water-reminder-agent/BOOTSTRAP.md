# 🚀 BOOTSTRAP.md — First-Run Ritual

> **File purpose:** One-time first-run ritual. Only created for a brand-new workspace. Delete it after the ritual is complete.
>
> ⚠️ **Delete this file once the ritual is complete.**

---

## Purpose

Walk through the setup steps the first time this agent is deployed. After completion, this file should be removed from the workspace.

---

## First-Run Checklist

### 1. Set Your iMessage Recipient
Open `USER.md` and fill in the `iMessage Recipient` field with your phone number or Apple ID email.

### 2. Set Your Timezone
Fill in the `Timezone` field in `USER.md` so quiet-hour logic works correctly.

### 3. Verify `imsg` Is Available
Run:
```
imsg send "<your-number>" "Water Reminder bootstrap test 💧"
```
Confirm the message arrives before proceeding.

### 4. Adjust Quiet Hours (Optional)
Edit `QUIET_START` and `QUIET_END` in `AGENTS.md` if the defaults (`22:00` / `08:00`) don't suit your schedule.

### 5. Adjust Interval (Optional)
Change `INTERVAL_MINUTES` in `AGENTS.md` if you prefer a cadence other than 60 minutes.

### 6. Run a Dry-Run Heartbeat
Trigger one manual heartbeat tick and confirm:
- A message is sent successfully.
- A log entry is written to `LOG_FILE`.

### 7. Enable Scheduled Runs
Configure your scheduler (cron, launchd, or the gateway) to invoke the agent's heartbeat at the desired interval.

### 8. Delete This File
Remove `BOOTSTRAP.md` from the workspace. Its job is done.

---

*Delete this file once the bootstrap ritual is complete.*
