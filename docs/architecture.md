# Architecture Notes

## Core pattern
A central orchestrator coordinates specialized agents rather than expecting a single general-purpose agent to manage the full workflow.

## Why this pattern fits enterprise CRM workflows
- Different actions have different data needs
- Profitability and compliance checks require explicit guardrails
- Operational steps need structured output, not just free-text recommendations
- Exceptions should be surfaced intentionally rather than buried in a chat response

## Agent responsibilities

### 1. Lead Generation Agent
Inputs:
- account history
- segment signals
- opportunity indicators

Outputs:
- lead score
- rationale
- recommended next action

### 2. Order Form Creation Agent
Inputs:
- approved account/opportunity context
- pricing or order prerequisites

Outputs:
- structured order inputs
- missing-field checklist
- workflow handoff recommendation

### 3. Profitability & Credit Agent
Inputs:
- account financial signals
- revenue realization data
- credit utilization patterns

Outputs:
- profitability status
- credit risk flags
- intervention recommendation

### 4. Compliance Agent
Inputs:
- policy thresholds
- account status
- workflow context

Outputs:
- pass / flag / block decision
- reason codes
- escalation path

### 5. Predictive Impact Agent
Inputs:
- account trends
- historical outcomes
- revenue and utilization patterns

Outputs:
- likely future account impact
- confidence band
- prioritization guidance

## Design principles
- Human-readable rationales
- Explicit escalation paths
- Guardrails before action completion
- Structured outputs for downstream workflows
- Predictive signals tied to operational decisions
