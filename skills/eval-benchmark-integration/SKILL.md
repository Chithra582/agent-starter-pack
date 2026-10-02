---
name: eval-benchmark-integration
description: Use when establishing evaluation suites, automated test benchmarks, and synthetic test datasets for GenAI agents.
---

# Eval Benchmark Integration

## Overview
Embeds quantitative evaluation frameworks and automated benchmark gates directly into the agent project lifecycle.

## When to Use
- When measuring response quality, tool invocation accuracy, or retrieval faithfulness.
- When establishing pre-commit or CI/CD quality gates that prevent regression deployments.
- When generating synthetic test cases from real or simulated conversational data.

## Core Capabilities
1. **Automated Rubric Scoring**: Computes faithfulness, answer relevance, and tool argument validity.
2. **Regression Detection**: Compares benchmark scores across git commits and fails builds if quality degrades.
3. **Synthetic Dataset Generation**: Creates grounded question-answer pairs to stress-test agent reasoning boundaries.
