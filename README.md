# Evaluate_with_replicates-for-RAGAS
This project extends the `evaluate()` function from [RAGAS](https://github.com/explodinggradients/ragas) to support **replicate runs**, enabling statistical analysis such as:

- Mean
- Standard deviation
- Min / Max
- Median
- Confidence intervals (95%)

## Why?

When comparing models using custom benchmarks in RAG pipelines, single-run metrics aren’t enough. Repeating evaluations with multiple replicates yields **statistically significant insights**.

> Inspired by: [RAGAS Issue #109 – Statistical Replicates for Evaluate](https://github.com/explodinggradients/ragas/issues/109)

## Features

-  Run `evaluate()` N times in parallel (`num_replicates=30`)
-  Aggregate all metrics
-  Return detailed statistics
-  Integrates seamlessly with existing RAGAS workflows

## Usage

```python
from ragas_evaluate_replicates import evaluate_with_replicates

# Example call
result = evaluate_with_replicates(
    dataset=my_eval_dataset,
    metrics=my_metrics,
    num_replicates=30,
    show_progress=True
)

print(result)
