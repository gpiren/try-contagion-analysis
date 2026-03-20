# TRY Contagion Analysis

This project investigates whether Turkish Lira (TRY) crisis events generate financial contagion effects across emerging market currencies (BRL, MXN, ZAR) and Turkish equities (BIST 100).

Using daily return data from 2018 to 2025, the notebook applies:

- Correlation and rolling correlation analysis
- Crisis-window comparisons (±5 trading days around volatility-adjusted TRY shock days)
- T-tests comparing rolling correlations during crisis vs. normal periods
- Event study methodology with Cumulative Abnormal Returns (CAR) using per-event baselines
- VIX-controlled Granger causality testing
- Contagion network diagram

## Methodological Notes

Crisis days are identified using a volatility-adjusted threshold: days where TRY depreciation exceeds 2 standard deviations of its own 30-day rolling volatility, rather than a fixed 3% cutoff. Event windows use trading-day index positions rather than calendar days. CAR baselines are computed per event from t-120 to t-10 trading days before each shock.

## Findings

- BRL shows the strongest and most significant correlation regime shift during TRY crisis windows (p=0.000), despite having no stable baseline relationship with TRY.
- MXN correlations are significantly lower during crisis windows than in normal periods (p=0.004), suggesting decoupling rather than contagion once global risk-off effects are filtered out.
- ZAR and BIST show no statistically significant regime change during crisis windows.
- CAR analysis finds no statistically significant abnormal returns for any asset across the 81 crisis events, though BIST shows the largest directional response (-0.65%).
- Granger causality tests find no evidence that TRY returns predictively lead any of the four assets at lags 1 or 2, suggesting contagion is episodic and event-driven rather than a stable daily transmission mechanism.
- The contagion network confirms that EM currencies primarily co-move with each other during crisis windows, while BIST is more responsive to VIX than to TRY directly.

## Conclusion

TRY crises, when properly isolated from global risk-off noise, have a narrower contagion footprint than raw correlations suggest. The dominant transmission channel appears to operate through investor behavior during extreme events rather than persistent structural linkages.
