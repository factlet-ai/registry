# Factlet Protocol — example registry

Community-contributed example Factbooks for the [Factlet Protocol](https://factlet.ai). Real artifacts that implementers and users can read, fork, and learn from.

## Browse

| Domain | Path | Highlights |
|---|---|---|
| **Payments (Stripe)** | [`examples/payments`](examples/payments) | money handling, refund workflow, supersession example |
| **React + TypeScript frontend** | [`examples/frontend`](examples/frontend) | retired-tech (Redux), a11y floor, bundle budget |
| **ML training pipeline** | [`examples/ml-pipeline`](examples/ml-pipeline) | data lineage, eval gates, PII handling |

Each directory contains `factbook.yaml` + `README.md` explaining what the example illustrates and how to use it.

## Contribute

See [CONTRIBUTING.md](CONTRIBUTING.md). What's expected of a registry contribution:

- Schema-valid against the [v0.1 spec](https://github.com/factlet-ai/spec/blob/main/SPEC.md)
- No secrets, no PII, no proprietary content
- Sanitized example — fictional but realistic
- README explaining the domain, what's interesting about the facts, and how to test the AI's compliance with them
- 5-10 factlets minimum, focused on facts an AI would otherwise get wrong

## Validate

Once the [reference SDK](https://github.com/factlet-ai/reference-sdk) ships, run:

```bash
factlet validate examples/<your-domain>/factbook.yaml
```

For now, validate manually against [the schema](https://github.com/factlet-ai/spec/tree/main/schema).

## License

Examples in this repository are MIT-licensed. See [LICENSE](LICENSE).
