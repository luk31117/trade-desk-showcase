# Workflow Examples

These examples describe the system behavior without exposing private implementation details.

## Trade Desk Review

1. Load the watchlist and market data.
2. Score tickers using fundamentals, valuation, volume, technical context, and local signal state.
3. Show LK V1 state across multiple timeframes.
4. Display backtest context and optimization metadata where available.
5. Compare Market Intelligence setup status with local Trade Desk evidence.
6. Send qualified names to Suggested Focus or portfolio review.

## Market Intelligence Setup Flow

1. Run one or more research modules.
2. Generate ticker candidates with evidence and limitations.
3. Build short-, medium-, and long-term setup views.
4. Store each setup as a structured snapshot.
5. Re-check saved setups against later market data.
6. Mark outcomes as waiting, open, won, lost, expired, or invalidated.

## Active Portfolio Review

1. Define a strategy allocation.
2. Assign target weights by ticker.
3. Monitor current paper positions and allocation drift.
4. Review Smart Rebalance proposals.
5. Apply paper-trading safeguards before any order action.
6. Store execution logs and portfolio snapshots for review.

## Example Safeguards

- Do not act on stale signals.
- Prevent duplicate signals from creating repeated orders.
- Require owner-level permissions for mutating actions.
- Block invalid orders.
- Use provider fallback handling and failure logs.
- Keep paper-trading mode during testing.
