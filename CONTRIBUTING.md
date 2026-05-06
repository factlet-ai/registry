# Contributing example factbooks

The registry collects example Factbooks across domains so implementers and protocol users have real artifacts to learn from.

## What belongs here

- Factbooks demonstrating a domain (payments, ML pipeline, frontend conventions, regulated industry, etc.)
- Factbooks demonstrating a feature of the protocol (supersession chains, archived facts, FactSignal scoring edge cases)
- Synthetic + sanitized examples preferred over real internal data

## What does NOT belong here

- Factbooks containing real customer data, secrets, API keys, or PII
- Factbooks copied from a private codebase without sanitization
- Auto-generated junk

## Adding a factbook

1. Create a directory under `examples/<domain>/` (e.g. `examples/payments/`).
2. Add `<domain>-factbook.yaml` conforming to the v0.1 schema (see [factlet.ai/protocol](https://factlet.ai/protocol)). Filename follows the `<scope>-factbook.yaml` convention.
3. Add `README.md` explaining: the domain, what facts are interesting, and what the example illustrates.
4. Run the validator (once published): `factlet validate examples/<domain>/<domain>-factbook.yaml`.
5. Open a PR.

## Review criteria

- Schema-valid against the published v0.1 spec
- No secrets, no PII, no proprietary content
- README clearly explains what the example teaches
- Factlet IDs, statements, and confidence scores are realistic

## Code of Conduct

Participation requires adherence to the [Code of Conduct](CODE_OF_CONDUCT.md).
