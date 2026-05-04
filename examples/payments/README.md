# Example: payments-stripe

A sanitized Factbook for a fictional Stripe-based payments service.

## What this example illustrates

- **Architecture facts** (f001): the team's chosen integration pattern (webhooks over polling). Prevents the AI from suggesting polling-based code.
- **Compliance constraint** (f002): the 90-day refund rule — a real regulatory/policy boundary that an AI would not know without grounding. This is the kind of fact whose absence ships compliance bugs.
- **Anti-pattern with provenance** (f003 + f900): demonstrates supersession. The team had an old fact (f900: customer IDs as int) that caused an overflow incident on 2026-01-15. f900 was archived with a reason, and f003 (strings, not int) supersedes it. Future AI reads see only f003 but the audit trail remains.
- **Format conventions** (f004, f005, f006): integer cents, idempotency key shape, currency conversion timing — small but high-friction details.
- **Operational** (f007): on-call escalation rules.

## How to use

Copy `factbook.yaml` into your AI tool of choice (e.g. via [factlet.ai/getting-started](https://factlet.ai/getting-started) Prompt 2). Ask questions like:

- "Add an endpoint to refund a 6-month-old payment automatically." (Should defer to f002 and refuse auto-processing.)
- "Store the Stripe customer ID in our user table." (Should cite f003: string, not int.)
- "Convert the prices to EUR before saving." (Should cite f006: convert at display time only.)

If the AI ignores any of these factlets, it's not properly using the Factbook — flag the integration.

## Adapt to your project

Replace the team name, source paths, and incident references with your own. Aim for 5-10 factlets covering decisions an AI would otherwise get wrong; expand from there.
