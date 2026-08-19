# Workflow Examples

These examples describe the system behavior without exposing private implementation details.

## Trade Desk Review

1. Load the watchlist and market data.
2. Score tickers using fundamentals, valuation, volume, technical context, and local signal state.
3. Show LK V1 state across multiple timeframes.
4. Display backtest context and optimization metadata where available.
5. Compare Market Intelligence setup status with local Trade Desk evidence.
6. Send qualified names to Suggested Focus or portfolio review.

## Trade Desk And Market Intelligence Bridge

1. Trade Desk can launch a ticker-level Market Intelligence deep dive in Trade Desk mode.
2. The request includes local context such as LK V1 state, timeframe stack, scores, relative volume, backtest metrics, and local signal reasons.
3. Market Intelligence uses that local context as an execution-validation lens rather than treating external research as a standalone signal.
4. Market Intelligence results can link selected names back into Trade Desk for local signal and risk review.
5. Active Portfolio rebalance review can optionally refresh Market Intelligence evidence before approving, reducing, or rejecting paper rebalance actions.

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
5. Save promising ideas as local monitors for later validation in Trade Desk or a real backtest engine.

## Backtest Context Review

1. Run staged LK V1 configuration sweeps across selected tickers and timeframes.
2. Store simulated trade count, win rate, ROI, maximum drawdown, profit factor, and score.
3. Show the result beside the current signal state so backtest context does not override live setup quality.
4. Prefer rows with enough trade count and controlled drawdown over eye-catching low-sample results.
5. Treat all results as research context until forward-tested.

## Active Portfolio Review

1. Define a strategy allocation.
2. Assign target weights by ticker.
3. Monitor current paper positions and allocation drift.
4. Review Smart Rebalance proposals.
5. Apply paper-trading safeguards before any order action.
6. Store execution logs and portfolio snapshots for review.

## Operational Workflow Mapping

The private implementation is organized so each trading workflow leaves a review trail:

- **Market-data refresh**: updates the local universe, prices, relative volume, score inputs, and signal context before research or portfolio review.
- **Signal synchronization**: checks multi-timeframe LK V1 states and stores the current trend, indicator state, flip timing, and backtest context.
- **Allocation-drift review**: compares target allocation with current paper positions so portfolio review can focus on exceptions rather than manual inspection.
- **Paper execution review**: tracks order intent, permissions, order state, execution logs, and failures before treating a rebalance as complete.
- **Outcome monitoring**: checks saved setups against later prices and marks whether the idea is waiting, active, won, lost, expired, or invalidated.

## Example Safeguards

- Do not act on stale signals.
- Prevent duplicate signals from creating repeated orders.
- Require owner-level permissions for mutating actions.
- Block invalid orders.
- Use provider fallback handling and failure logs.
- Keep paper-trading mode during testing.
- Use conservative handling when an outcome sequence is ambiguous.
