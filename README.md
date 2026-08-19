# LK Intelligence / LK V1 Trade Desk

**A private trading research and paper-trading operations platform that turns market ideas into structured, testable, and reviewable decisions.**

LK Intelligence connects signal validation, AI-assisted market research, event-driven strategy research, portfolio allocation, paper execution review, and post-trade outcome tracking. This public repository is a sanitized showcase of the product, architecture, workflows, screenshots, and risk controls.

The full implementation remains private to protect strategy logic, credentials, execution workflows, and account-specific data. Architecture decisions and selected implementation details can be discussed selectively upon request.

## Start Here

- [Architecture](docs/architecture.md): how the modules connect.
- [Workflow Examples](docs/workflows.md): how research, validation, safeguards, and outcome tracking work.
- [Signal Review Example](snippets/signal-review-example.md): sanitized example of structured setup review.
- [Event Strategy Example](snippets/event-strategy-lab-example.md): sanitized prompt thesis and event-rule workflow.
- [Public Scope](docs/public-scope.md): what is intentionally included and excluded.

## Product Snapshot

| Module | What It Does | Why It Matters |
| --- | --- | --- |
| **Trade Desk** | Validates tickers against LK V1 signal states, fundamentals, volume, backtest context, setup status, and risk checks. | Prevents research ideas from moving toward execution review without local evidence. |
| **Market Intelligence** | Runs opportunity scans, ticker deep dives, decision briefs, watchlists, setup snapshots, and outcome tracking. | Turns broad market evidence into structured research that can be reviewed later. |
| **Event Strategy Lab** | Separately converts macro, policy, commodity, earnings, weather, and corporate catalysts into event rules and validation plans. | Turns discretionary catalysts into testable hypotheses instead of one-off opinions. |
| **Active Portfolio** | Supports target allocation, allocation-drift checks, Smart Rebalance, paper position/order monitoring, and execution logs. | Connects research to portfolio review while keeping execution controlled and auditable. |

## Screenshots

### Trade Desk Overview

Universe-level dashboard for synced tickers, multi-timeframe LK V1 states, fundamentals, volume, technical scores, backtest context, Market Intelligence status, and Suggested Focus review.

![Trade Desk Overview](docs/screenshots/trade-desk-overview.png)

### GOOGL Backtest Context

Backtest context shown beside live signal state. The purpose is to support research review while avoiding blind reliance on a single optimized result.

![GOOGL Backtest Context](docs/screenshots/googl-backtest-context.png)

### Market Intelligence Overview

Research workspace for module-based opportunity discovery, ticker deep dives, decision briefs, watch levels, and setup generation.

![Market Intelligence Overview](docs/screenshots/market-intelligence-overview.png)

### Event Strategy Deep Dive

Detailed strategy view showing thesis, trigger logic, preliminary feasibility, allowed filters, forbidden filters, validation protocol, and robustness checks.

![Event Strategy Lab Deep Dive](docs/screenshots/event-strategy-lab-deep-dive.png)

### Sports Probability Lab

Experimental probability workspace for odds, implied probability, modeled probability, edge, watch levels, and outcome review. It is included as a decision-quality lab rather than a core trading module.

![Sports Probability Watchlist](docs/screenshots/sports-probability-watchlist.png)

## What Makes It Interesting

- **Research is forced into structure**: ideas are stored with evidence, setup type, entry/stop/target logic, holding period, status, and later outcome.
- **Backtests are context, not permission**: historical results are displayed beside live signal quality, drawdown, sample size, and current risk state.
- **AI is constrained**: prompts push outputs into repeatable hypotheses, allowed filters, forbidden filters, validation steps, and failure modes.
- **Operations are treated seriously**: stale signals, duplicate signals, invalid orders, provider failures, permissions, and failure logs are part of the workflow.
- **The project is productized**: it is not a notebook; it is a dashboard with research modules, state management, persistence, review flows, and paper-trading controls.

## Actual Workflow Relationship

Trade Desk and Market Intelligence are connected. Trade Desk can run ticker-level Market Intelligence deep dives with local LK V1 state, score quality, backtest metrics, relative volume, and signal context. Market Intelligence can also route selected names back into Trade Desk through review links.

Event Strategy Lab is separate. It creates catalyst-driven strategy hypotheses and saved monitors that would need later validation in Trade Desk or a dedicated backtest engine before automation.

```text
Market data, fundamentals, watchlist inputs
        |
        v
Trade Desk local scoring and LK V1 state validation
        |\
        | \--> Market Intelligence discovery, ticker deep dives, decision briefs, and setup snapshots
        |      ^       |
        |      |       v
        |      +-- optional Trade Desk context and "Review in Trade Desk" links
        |
        +----> Event Strategy Lab catalyst scans, event rules, validation plans, and saved monitors
        |
        v
Trade Desk review of qualified ideas against local signal, score, volume, and risk evidence
        |
        v
Active Portfolio allocation, Smart Rebalance, and paper execution logs
        |
        v
Outcome monitoring for saved setups, portfolio snapshots, and execution review
```

## Implementation Highlights

- Multi-timeframe signal dashboard covering 38 equities and eight configured timeframes.
- Backtest context surfaced alongside live signal state, including simulated trades, win rate, ROI, drawdown, profit factor, and configuration metadata.
- Market Intelligence workflows covering 160 tickers and 540 saved setup snapshots in the private system.
- Scheduled refresh and synchronization logic for market data, signal state, setup status, portfolio state, and review logs.
- Operational safeguards for stale signals, duplicate signals, invalid orders, provider failures, owner-gated actions, and paper-trading review.
- Private Next.js/TypeScript application with API integrations, persistence, dashboard state management, and public/private repo separation.

## Research Examples

- **GOOGL staged strategy sweep**: one representative GOOGL 2D long-only LK V1 configuration produced 70 simulated trades, 57.1% win rate, 2.99 profit factor, 509.9% ROI, and 20.9% maximum drawdown after 0.1% commission assumptions. This is shown as research/backtest context, not a live performance claim.
- **Market Intelligence setup tracking**: saved setup snapshots are monitored for entry activation, take-profit, stop-loss, expiry, realized return, and ambiguous outcome handling.
- **Event Strategy Lab**: current catalysts are converted into repeatable event rules, sector/ticker baskets, entry and exit logic, failure modes, validation protocols, and saved strategy monitors.

## Questions The Project Explores

- How should a market idea move from news, price action, or a model signal into a reviewable setup?
- How do you stop a dashboard from becoming an overfitting machine?
- What information should be visible before a rebalance or paper order is allowed?
- How should AI-assisted research be constrained so it produces structured hypotheses instead of loose opinions?
- How do you create enough traceability to review whether a trading idea actually worked?

## Public Scope

This repository includes product overview, screenshots, architecture notes, sanitized workflow examples, and public explanation of design decisions and system boundaries.

It does **not** include private API keys, environment files, full LK V1 strategy implementation, proprietary Pine Script, paper/live execution code, private portfolio state, private Supabase data, account-specific records, or private strategy monitors.

## Disclaimer

This showcase is for technical and portfolio review only. It is not financial advice, an investment recommendation, or a live trading system.
