# LK V1 Trade Desk Showcase

This is a public, sanitized showcase for **LK V1 Trade Desk**, a private trading research and paper-trading operations project.

The full implementation is intentionally private. This repository is designed to show the product thinking, workflow design, and system architecture without exposing proprietary strategy logic, credentials, execution code, or private trading data.

## Product Overview

LK V1 Trade Desk connects three workflows:

- **Trade Desk**: validates market ideas against local LK V1 signal states, fundamentals, volume, backtest context, AI setup status, and risk checks.
- **Market Intelligence**: discovers opportunities, runs ticker-level research, generates short/medium/long setup views, and tracks saved setup outcomes.
- **Active Portfolio**: supports paper-trading strategy allocation, target weights, allocation-drift checks, Smart Rebalance, position/order monitoring, and execution logs.

The goal is to turn market ideas into structured, reviewable trading workflows rather than one-off discretionary notes.

## What This Demonstrates

- Systematic trading research workflow design.
- Market-data validation and multi-timeframe signal monitoring.
- AI-assisted research with evidence and outcome tracking.
- Portfolio allocation, risk checks, and paper-trading operations.
- Trading dashboard UX for decision review, not blind automation.
- TypeScript/Next.js application design and production-minded safeguards.

## Technical Areas

- Frontend product workflow design in Next.js and TypeScript.
- Market-data and signal-state normalization.
- Multi-timeframe dashboard state and scoring.
- AI-assisted research orchestration and structured setup storage.
- Paper-trading operations concepts: allocation drift, rebalance review, safeguards, and logs.
- Documentation and public/private repo separation for protecting proprietary logic.

## Screenshots

### Trade Desk Overview

![Trade Desk Overview](docs/screenshots/trade-desk-overview.png)

### Trade Desk Backtest Context

![Trade Desk Backtest Context](docs/screenshots/trade-desk-backtest-tooltip.png)

### Suggested Focus Ask Me

![Suggested Focus Ask Me](docs/screenshots/suggested-focus-ask-me.png)

### Market Intelligence Overview

![Market Intelligence Overview](docs/screenshots/market-intelligence-overview.png)

### Market Movers Scan

![Market Movers Scan](docs/screenshots/market-movers.png)

## System Flow

```text
Market data, fundamentals, watchlist inputs
        |
        v
Trade Desk local scoring and LK V1 state validation
        |
        v
Market Intelligence discovery, ticker deep dives, and setup snapshots
        |
        v
Trade Desk review of AI ideas against local signal, score, volume, and risk evidence
        |
        v
Active Portfolio allocation, Smart Rebalance, and paper execution logs
        |
        v
Outcome monitoring for saved setups, portfolio snapshots, and execution review
```

## Key Design Principles

- **Evidence-gated decisions**: AI-generated or external market ideas must be validated against local signal, score, volume, and risk evidence.
- **Paper trading first**: execution workflows are designed for paper trading and forward-testing before any live use.
- **Traceability**: setup snapshots, execution logs, and outcome monitoring make it possible to review decisions after the fact.
- **Safety over automation**: stale signals, duplicate signals, allocation breaches, invalid orders, and provider failures are treated as first-class risks.

## Public Scope

This repository includes:

- Product overview.
- Screenshots.
- Architecture notes.
- Sanitized workflow examples.

This repository does **not** include:

- Private API keys or environment files.
- Full LK V1 strategy implementation.
- Proprietary Pine Script.
- Paper/live trading execution code.
- Private portfolio state.
- Private Supabase data.

## Documentation

- [Architecture](docs/architecture.md)
- [Workflow Examples](docs/workflows.md)
- [Public Scope And Privacy](docs/public-scope.md)

## Disclaimer

This showcase is for technical and portfolio review only. It is not financial advice, an investment recommendation, or a live trading system.
