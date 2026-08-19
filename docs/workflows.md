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
2. Select market coverage, risk profile, and strategy direction.
3. Generate ticker candidates with evidence and limitations.
4. Build a Decision Brief and Trade Today / Watch Levels shortlist.
5. Build short-, medium-, and long-term setup views for selected names.
6. Store selected setups into research journals as structured snapshots.
7. Re-check saved setups against later market data.
8. Mark outcomes as waiting, open, won, lost, expired, or invalidated.

## Event Strategy Lab Flow

1. Scan for repeatable event-driven strategy candidates.
2. Convert catalysts into trigger rules, impacted sectors, and ticker baskets.
3. Draft entry rules, exit rules, failure modes, and monitoring logic.
4. Label preliminary historical feasibility and overfit risk.
5. Save promising ideas as monitors for later validation in Trade Desk or a real backtest engine.

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
- Use conservative handling when an outcome sequence is ambiguous.
