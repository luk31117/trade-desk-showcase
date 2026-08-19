# Architecture

LK Intelligence is organized around four product layers: research discovery, event strategy research, local validation, and paper-trading operations.

## 1. Trade Desk

Trade Desk is the local validation layer. It brings together:

- Watchlist and market-data coverage.
- LK V1 state across multiple timeframes.
- Fundamental, valuation, volume, technical, and total scores.
- Backtest context and optimization metadata.
- Market Intelligence setup status.
- Suggested Focus cards for trader and investor review.

The central design idea is that external research is useful, but it should not override weak local evidence. A ticker needs sufficient local support before moving from idea to execution review.

## 2. Market Intelligence

Market Intelligence is the opportunity-discovery layer. It supports:

- Research modules such as institutional positioning, earnings volatility, sector leadership, macro policy watchlists, hidden gems, and market movers.
- Market coverage filters across global and regional universes.
- Risk profile and strategy-direction filters for conservative, balanced, aggressive, long-only, and long/short research modes.
- Single-ticker deep dives.
- Decision Brief and Trade Today / Watch Levels views for daily research triage.
- Short-, medium-, and long-term setup generation.
- Entry, stop loss, take profit, probability, expected ROI, and holding-period fields.
- Setup journals, setup history, and realized-outcome tracking.

The output is structured so research can be reviewed and compared over time.

## 3. Event Strategy Lab

Event Strategy Lab converts market-moving catalysts into strategy research plans. It supports:

- Macro, policy, weather, commodity, social, and corporate catalyst scanning.
- Repeatable trigger definitions rather than one-off stock tips.
- Affected sector and ticker mapping.
- Preliminary 5Y/10Y feasibility estimates when available.
- Entry and exit rules, failure modes, and validation protocols.
- Saved monitors for event triggers that should be tested later.

This layer is designed to turn discretionary event observations into testable trading hypotheses.

## 4. Active Portfolio

Active Portfolio is the paper-trading operations layer. It supports:

- Strategy-level allocation.
- Target weights by ticker.
- Allocation-drift checks.
- Smart Rebalance review.
- Position and order monitoring.
- Execution logs and portfolio snapshots.

This layer is designed for paper trading and operational review, not unattended live execution.

## Data Flow

```text
Market Data / Fundamentals / Watchlist
        |
        v
Trade Desk scoring and LK V1 state checks
        |
        v
Market Intelligence research modules and setup snapshots
        |
        v
Event Strategy Lab catalyst research and strategy monitors
        |
        v
Trade Desk local validation
        |
        v
Active Portfolio review, rebalance, and paper execution logs
```

## Safety Controls

The private implementation includes controls around:

- Stale signals.
- Duplicate signals.
- Allocation limits.
- Execution permissions.
- Invalid order handling.
- Provider failures and fallbacks.
- Paper-trading enforcement during testing.
- Outcome tracking for saved setups.
- Manual review before execution-sensitive actions.

Only a sanitized overview is included in this public showcase.
