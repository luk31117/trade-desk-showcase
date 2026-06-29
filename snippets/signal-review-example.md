# Sanitized Signal Review Example

This is a simplified example of the decision structure used by the private project. It is not production code.

```text
Input:
  ticker
  local signal state
  timeframe stack
  fundamental score
  volume score
  risk flags
  market intelligence setup

Review:
  1. Check whether the signal is fresh or stale.
  2. Check whether multiple timeframes agree.
  3. Compare AI setup direction with local signal state.
  4. Reject or downgrade if volume/risk evidence is weak.
  5. If still valid, send to portfolio review rather than auto-execute.

Output:
  decision: Review / Wait / Avoid
  reason
  risks
  next checks
```

The private implementation contains the actual scoring, persistence, and dashboard logic.
