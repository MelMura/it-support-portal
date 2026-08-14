# Hardware Replacement Request Flow

**Situation:** A device — a laptop, a classroom projector, a mouse, a router — is
damaged, failing, or has reached end of life, and needs to be replaced rather than
repaired. This guide is less a technical fix and more a **process**: who does what, in
what order, so a request doesn't stall between "it's broken" and "here's the new one."

> 🇩🇪 **Auf Deutsch:** hardware = *Hardware* · a support ticket = *ein Ticket* /
> *eine Anfrage* · to escalate = *eskalieren* · a replacement = *ein Ersatzgerät*.

## The Flow

1. **Report** — The user (or the person who noticed the fault) logs it: what the device
   is, what's wrong, and since when. A vague report ("laptop doesn't work") costs time
   later, so this step should capture at minimum: device ID/asset tag, symptom, and date
   first noticed.
2. **Triage** — Someone confirms it's actually a hardware fault and not something
   fixable in software (a driver issue, a loose cable, a setting). This step exists to
   stop working hardware from being replaced unnecessarily.
3. **Confirm no repair path** — Check whether the fault is covered by warranty or is a
   quick, cheap fix (e.g. a replacement charger vs. a whole new laptop). Not every fault
   needs a full replacement.
4. **Request approval** — For anything above a small threshold, whoever manages the
   budget needs to sign off before a purchase or stock item is issued. This is usually
   the step that stalls a request the longest, so it should be flagged clearly rather
   than left implicit.
5. **Issue the replacement** — From existing stock if available, or ordered if not. The
   old device is logged as retired/decommissioned so the asset list stays accurate — a
   surprisingly common gap in informal setups.
6. **Confirm with the user** — The person who reported it confirms the replacement
   resolves the issue, and the ticket is closed. Closing the loop matters: an
   unconfirmed "fix" that quietly fails again just becomes a second, harder-to-trace
   report later.

## A Minimal Ticket Template

```
Device / Asset ID:
Reported by:
Date first noticed:
Symptom:
Triage result (software fix / hardware fault / needs replacement):
Approval status:
Replacement issued (date, device):
Old device retired (Y/N):
Confirmed resolved by user (Y/N):
```

## When to Escalate

- The same device model keeps failing across multiple users — worth flagging as a batch
  issue (a bad stock order, a manufacturing fault) rather than logging each one
  separately.
- The fault might be a safety issue (frayed cabling, overheating, a device that's been
  physically damaged) — this skips the normal queue and gets pulled out for immediate
  attention.
- Approval is stuck and the device is blocking someone's actual work — this is worth a
  direct, polite nudge rather than waiting silently in a queue.
