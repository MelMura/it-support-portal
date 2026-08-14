# IT Service &amp; Troubleshooting Portal

A small internal-style knowledge base for a school IT helpdesk — written the way I'd
document real support work: what the problem looks like, why it happens, and the exact
steps to fix it. Built with [Docsify](https://docsify.js.org) and hosted on GitHub Pages,
so it's a live, searchable site rather than a plain document.

## Why this exists

I'm preparing for a Fachinformatiker / Elektroniker Ausbildung in Germany and currently
support the IT side of things at my school. Writing this portal was a way to practise the
part of the job that doesn't show up on a CV: turning a fix you've worked out once into
something a colleague — or your future self — can follow without you in the room.

## Guides in this portal

| Guide | Covers |
|---|---|
| [Fixing DNS Resolution Issues](guides/dns-resolution.md) | "Can't reach this site" / "server not found" errors on a client machine |
| [VPN Client Setup Guide](guides/vpn-setup.md) | Setting up and troubleshooting a client VPN connection |
| [Hardware Replacement Request Flow](guides/hardware-replacement.md) | The process from "this device is broken" to a replacement in hand |

Use the sidebar or the search bar (top left) to jump straight to a guide.

## A note on how I write these

Every guide follows the same shape on purpose — **Symptom → Likely Causes → Step-by-Step
Fix → When to Escalate** — because a support document someone is reading *while something
is broken* should never make them hunt for the part they need. Consistency is part of the
documentation, not just the content.

Where it's useful, I've added the German technical term alongside the English one — partly
because I'm studying German for my Ausbildung, partly because a support document is only
useful if the person reading it recognises the words.

---
*Melissa Muradzikwa · [Portfolio](https://melissa-muradzikwa.vercel.app) · Built as a self-study project*
