# Azure ML Compute Cost & Utilization Queries

Curated Log Analytics Kusto scripts to: (1) estimate per‑pipeline cost, (2) highlight underutilized compute. Minimal hand‑editing required.

## Queries

| File                        | Purpose                                                             |
| --------------------------- | ------------------------------------------------------------------- |
| `cost-per-job.kql`          | ⇒ cost per Pipeline / Job (RootRunId) & submitter.                  |
| `underutilized-compute.kql` | Run‑level CPU / GPU utilization stats ⇒ flags low GPU or CPU usage. |

## Quick Tweak Points

- `declare query_parameters` blocks: change `lookback`, thresholds, duration filter.
- Pricing datatable: extend with your VM sizes / priorities (/ region) to improve accuracy.
- Underutilization heuristics: adjust thresholds until false positives are tolerable.

## Drill‑Down

In `underutilized-compute.kql` set `runId` at bottom to plot time‑binned utilization for a flagged run.

## Extensible Ideas

- Region‑specific pricing (add `Location` join)
- Persist summaries to a custom table for dashboards

---

Questions / suggestions → open an issue or drop a comment in the query.
