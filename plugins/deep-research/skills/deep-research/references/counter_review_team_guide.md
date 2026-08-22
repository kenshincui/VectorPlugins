# Counter-Review Worker Guide

Use this reference during P6 when the host supports independent parallel
workers. When it does not, run the same four perspectives sequentially.

## Inputs

Prepare:

- `draft_report.md`
- `citation_registry.md`
- task notes
- P0 configuration including `AS_OF`, mode, and source policy

## Review perspectives

1. **Claim validator** — trace every important claim to approved evidence;
   identify unsupported numbers, causal claims, and overconfident wording.
2. **Source diversity reviewer** — check official-source share, unique domains,
   concentration, source independence, and accessibility labels.
3. **Recency reviewer** — verify publication dates and flag evidence that is
   stale for the topic's change rate.
4. **Contradiction finder** — look for conflicting facts, alternative causal
   explanations, missing stakeholder perspectives, and counterexamples.

## Dispatch

- Dispatch the four reviews concurrently only through capabilities the current
  host actually exposes.
- Give each worker the same input set but only one review perspective.
- Require findings to include severity, affected claim or section, evidence,
  and a concrete correction.
- If parallel workers are unavailable, perform the four passes sequentially
  and preserve separate sections in the review record.

## Synthesis

Merge duplicates, retain disagreements, and classify issues as Critical, High,
Medium, or Low. Find at least three substantive issues; if fewer appear, repeat
the contradiction and evidence-trace passes instead of inventing findings.

All Critical issues must be resolved before P7. High issues must be fixed or
explicitly accepted with rationale. Preserve the review record with the report.

Output:

```markdown
# P6 Counter-Review

## Critical
- Claim/section:
- Problem:
- Evidence:
- Required correction:

## High
...

## Medium and Low
...

## Resolution status
- Fixed:
- Accepted risk:
- Open:
```
