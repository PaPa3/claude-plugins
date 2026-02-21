---
description: List LangSmith experiments with metrics
argument-hint: [name-filter]
allowed-tools: [mcp__langsmith__list_experiments]
---

# List LangSmith Experiments

## Arguments
$ARGUMENTS

## Instructions

1. Call `list_experiments` — optionally filter by name if an argument was provided.
2. Present results as a comparison table with columns: Name, Latency (p50/p99), Cost, Feedback score, Run count.
3. Highlight the best experiment by feedback score.
4. Offer to fetch detailed runs for any experiment.
