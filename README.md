# Market-regime-detector
This model detects market regime using market volatility, prices, OAS and 10 year treasury rates

**Project**: Multi-Asset Market Regime Detection via Hidden Markov Models
Objective Developed a probabilistic AI model to classify market environments into two distinct states—Calm (Expansionary) and Crisis (Contractionary)—to enhance systematic risk management and capital allocation.

**Methodology & Data Engineering** * Feature Universe: Integrated 20 years of daily SPY price data (as a US equity proxy) with macro-indicators from FRED, including 10-Year Treasury Rates and High-Yield Credit Spreads (OAS).

**Signal Processing**: Applied a 21-day rolling volatility window. To ensure a "walk-forward" compliant model and eliminate look-ahead bias, all features were normalized using an Expanding Window Z-score methodology.

**The Model:** Implemented a Gaussian Hidden Markov Model (HMM) using the Expectation-Maximization (EM) algorithm. The model was configured for 1,000 iterations to ensure convergence, with a fixed random state for reproducibility and traceability.

**Key Quantitative Insights * Volatility as an Amplifier:** The model identified Volatility as the most significant regime differentiator. Rather than just a standalone metric, volatility acts as a convex aggregator that amplifies stress signals originating in the rate and credit markets.

**Regime Characteristics**: The "Crisis" state is statistically characterized by negative expected returns and a sharp expansion in credit spreads.

**Performance Divergence:** Backtesting revealed a significantly higher Sharpe Ratio during "Calm" regimes. This validates the model’s utility as a systematic "circuit breaker," signaling when to maintain equity exposure versus when to implement defensive hedging or cash positions.

**Current Market Context**
Recent Regime Expansion: Analysis of the most recent data indicates that the market is currently situated in a sustained Calm (Expansionary) Regime. As visualized in the chart, the "Green" shading has dominated the recent window, reflecting stabilized credit spreads and low relative volatility.

**Model Responsiveness**: The model successfully ignored minor price fluctuations, remaining in the "Calm" state because the underlying macro drivers (OAS and Rates) did not signal a systemic breakdown. This suggests a robust environment for equity exposure under current conditions.
