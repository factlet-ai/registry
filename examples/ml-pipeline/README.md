# Example: ml-training-pipeline

A sanitized Factbook for an MLflow-based ML training and serving pipeline.

## What this example illustrates

- **Data lineage discipline** (f001): no raw S3 reads. AI suggesting `pd.read_parquet('s3://...')` should defer to the dataset registry.
- **Versioning convention** (f002): semver, not run IDs. AI suggesting "use the latest run ID" is wrong; semver tags are the contract.
- **Eval gates** (f003): a hard quality bar with three concrete metrics. AI proposing to ship a model without these checks is dangerous.
- **Deployment pattern** (f004): shadow before traffic shift. Captures a deliberate non-default choice (no blue/green).
- **Feature store separation** (f005): online vs offline boundary, with an incident citation showing what happens when it's violated.
- **Privacy floor** (f006): PII hashing rule. Critical compliance fact.
- **Cost discipline** (f007): queue selection. Small but high-impact for a budget-conscious team.
- **Drift monitoring** (f008): observability config that AI must respect when adding new features.

## How to use

Copy `factbook.yaml` and ask:

- "Train a fraud detection model and ship it to prod." (Should cite f003 — eval gates — and f006 — PII handling.)
- "Read the user_events table from S3 directly to speed up the experiment." (Should cite f001 and refuse, propose dataset registry.)
- "Deploy this model with blue/green rollout." (Should cite f004 and refuse, propose shadow deployment.)

## Adapt to your project

The cost / queue / drift specifics will vary heavily by team. The lineage and PII facts tend to be more universal. Start with 5-7 facts that, if violated, would cause an incident or compliance issue.
