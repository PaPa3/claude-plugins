---
name: langsmith-observability
description: "Use this skill when the user wants to: (1) inspect LLM traces, runs, or execution history in LangSmith, (2) list or search LangSmith projects, datasets, prompts, or experiments, (3) debug AI pipeline failures or errors in LangSmith, (4) analyze experiment results or evaluation metrics, (5) retrieve prompt templates from LangSmith, (6) check billing usage or token costs, (7) browse conversation thread history."
version: 1.0.0
---

# LangSmith Observability Skill

Use the LangSmith MCP server tools to help users inspect, debug, and analyze their LLM applications.

## Available MCP Tools

### Projects & Runs
- **`list_projects`** — list LangSmith projects (filter by name or dataset)
- **`fetch_runs`** — fetch runs/traces from one or more projects (supports FQL filters, pagination)

### Prompts
- **`list_prompts`** — list prompts (filter by visibility: public/private)
- **`get_prompt_by_name`** — retrieve a specific prompt by name

### Datasets & Examples
- **`list_datasets`** — list datasets (filter by name, type, ID, or metadata)
- **`read_dataset`** — get a single dataset by ID or name
- **`list_examples`** — list examples within a dataset
- **`read_example`** — get a single example with optional version history

### Experiments
- **`list_experiments`** — list experiments with latency, cost, and feedback metrics

### Threads
- **`get_thread_history`** — get conversation thread message history

### Billing
- **`get_billing_usage`** — fetch billing usage for a date range

## Workflow

### Debugging a failing run
1. `list_projects` to find the relevant project
2. `fetch_runs` with `filter` for errors (e.g. `has_error = true`) and the project name
3. Inspect run details — show inputs, outputs, errors, latency
4. Suggest fixes based on the error

### Comparing experiments
1. `list_experiments` to show available experiments with metrics
2. Compare latency, cost, and feedback scores
3. Highlight the best-performing experiment

### Retrieving a prompt
1. `list_prompts` to browse available prompts
2. `get_prompt_by_name` to fetch the exact template
3. Show the prompt template and variables

## Output Format

- Present run errors with clear error messages and context
- Show experiments as a comparison table with metrics
- Format prompts with their template variables highlighted
- Always link to the LangSmith UI when possible (construct URLs from project/run IDs)
