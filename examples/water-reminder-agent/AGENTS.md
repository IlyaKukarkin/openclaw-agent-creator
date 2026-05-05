# 📋 AGENTS.md — Operating Instructions

> **File purpose:** Operating instructions for the agent and how it should use memory. Loaded at the start of every session. Good place for rules, priorities, and "how to behave" details.

---

## Purpose

This file defines the runtime behaviour of the **Water Reminder** agent. It is loaded at the start of every session and governs scheduling, messaging, logging, and quiet-hour logic.

---

## Configuration

| Parameter | Default | Description |
|-----------|---------|-------------|
| `RECIPIENT` | *(set in USER.md)* | iMessage recipient (phone number or Apple ID) |
| `INTERVAL_MINUTES` | `60` | Minutes between reminders |
| `QUIET_START` | `22:00` | Start of quiet hours (local time) |
| `QUIET_END` | `08:00` | End of quiet hours (local time) |
| `LOG_FILE` | `~/.water-reminder/log.jsonl` | Path to the append-only send log |

---

## Runtime Rules

1. **On wake/start:** Check the current time against `QUIET_START` / `QUIET_END`. If inside quiet hours, sleep until `QUIET_END`.
2. **On interval tick:** Select a message variant (see below), send via `imsg`, log the result.
3. **On send failure:** Log the error with `status: "failed"`. Do **not** retry within the same interval.
4. **On quiet-hour entry:** Suppress the next scheduled send and resume after `QUIET_END`.

---

## Message Variants

Rotate through the following messages in order, cycling back after the last:

1. "💧 Time to drink some water!"
2. "Hydration check — grab a glass. 🥤"
3. "Your body is ~60% water. Top it up. 💧"
4. "Small habit, big impact: drink a glass of water now."
5. "Fun fact: even mild dehydration reduces focus by up to 20%. Drink up! 💧"

---

## Memory

- This agent has **no persistent session memory** beyond the send log.
- The send log (`LOG_FILE`) is append-only and is the sole source of historical truth.
- Configuration is re-read from this file on every session start.

---

## Update Log

| Date | Change |
|------|--------|
| 2026-05-05 | Initial version |
