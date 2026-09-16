# Analytics Engine

Social Radar turns normalized interaction events into explainable social metrics. The goal is to show useful trends without pretending to know activity that the connected platform does not expose.

## Design principles

1. **Observable data only** — scores use supported, user-authorized interaction signals.
2. **Explainable metrics** — individual scores have a clear meaning instead of being arbitrary labels.
3. **Time-aware analysis** — recent movement and long-term patterns are treated differently.
4. **Period-correct reporting** — monthly and yearly Wrapped views use their own relevant windows.
5. **Relative interpretation** — rankings are most useful when compared within one account's own interaction history.

## Core metrics

### Interaction Score

Measures the relative strength of observable interaction with a connection during the selected period. It can combine supported event frequency, recency, and event weighting.

### Reciprocity Score

Estimates how balanced observable interaction is between the connected account and another account. A high score means the relationship is comparatively two-sided in the available data; it does not imply anything about private behavior.

### Consistency Score

Measures whether interaction is distributed steadily over time rather than concentrated in one short burst.

### Momentum

Compares a recent period with a prior baseline to identify rising, stable, or declining interaction patterns.

### Social Score

Provides an account-level summary derived from multiple normalized signals. It is intended as a dashboard overview, not a judgment about a person's real-world relationships.

## Social Signals

The engine converts meaningful metric changes into concise product events, for example:

- a connection entering the Inner Circle;
- a sustained increase in interaction momentum;
- a sustained decrease across multiple periods;
- unusually high reciprocity;
- a new top connection for a selected period.

Signals are designed to require meaningful change rather than reacting to every small fluctuation.

## Wrapped generation

Wrapped uses the same normalized analytics layer as the dashboard, but aggregates it into a fixed reporting period.

Typical outputs include:

- total observable interactions;
- strongest connections;
- most active period;
- new or rising connections;
- reciprocity highlights;
- account-level trends;
- shareable story-format summary cards.

Monthly and annual views are calculated independently so an annual report is not accidentally based on a short rolling dashboard window.

## What the engine does not claim

Social Radar does not infer secret profile views, hidden browsing, private intent, or other activity that the provider does not expose. Product copy is written to distinguish measured interaction from interpretation.