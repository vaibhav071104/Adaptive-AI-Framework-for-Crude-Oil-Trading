# Adaptive-AI-Framework-for-Crude-Oil-Trading


PROJECT OVERVIEW
This research project developed an AI-driven trading system for crude oil that integrates machine learning with real-time sentiment analysis from financial news and social media. The system addresses the challenge of crude oil's high volatility due to geopolitical events, supply-demand shocks, and rapid news flows that traditional trading strategies cannot adapt to quickly enough.

CORE INNOVATION: SENTIMENT-CONDITIONED RANDOM FOREST
Unlike standard Random Forest models, our system introduces three key novelties:

Multi-modal Fusion: Combines technical price indicators (RSI, MACD, moving averages, volatility) with transformer-based sentiment features (FinBERT, VADER) and event flags (OPEC meetings, EIA reports)

Dynamic Trade Sizing: Position sizes are adjusted based on the alignment between model confidence and sentiment strength - full positions when both agree, reduced sizes when they conflict

Real-time Risk Controls: Embedded 5% trailing stop-loss, volatility circuit breakers, and comprehensive audit logging for regulatory compliance

DATA SOURCES

Daily OHLC WTI crude oil prices (2015-2025) from Yahoo Finance

Timestamp-aligned global financial news from NewsData.io

Sentiment extraction using VADER (social media) and FinBERT (financial news)

Technical indicators: log returns, moving averages (5/10/20/50), EMAs, MACD, RSI, rolling volatility, z-scores

Sentiment features: daily scores, 3-5 day rolling averages, lagged values (t-1, t-2), OPEC/EIA event flags

METHODOLOGY

Walk-forward validation simulating live trading conditions (no look-ahead bias)

Training on expanding windows, testing on future data

Comparison against Moving Average crossover and Mean Reversion baselines

Risk overlay testing with and without controls to measure impact

PERFORMANCE RESULTS (2023-2025 BACKTEST)
Our Sentiment-Conditioned Random Forest achieved:

Annualized Return: 18.5%

Annual Volatility: 13.0%

Sharpe Ratio: 1.42

Maximum Drawdown: -22.3%

Win Rate: 56.2%

Profit Factor: 1.48

Number of Trades: 384

Average Hold Time: 3.1 days

BASELINE COMPARISONS
Moving Average Strategy:

Annual Return: 10.2% (81% lower than our system)

Sharpe Ratio: 0.87

Max Drawdown: -24.5%

Mean Reversion Strategy:

Annual Return: 11.4% (62% lower than our system)

Sharpe Ratio: 0.93

Max Drawdown: -28.1%

KEY FINDINGS

Model Accuracy: 84.3% on training data, 48.1% out-of-sample (realistic for financial prediction)

Feature Importance: RSI and volatility were top technical features, but sentiment consistently ranked in top 5

Risk Control Impact: Stop-loss and circuit breakers reduced drawdowns by 30% without sacrificing returns

Crisis Performance: Largest performance gaps occurred during high-news-volume periods, validating sentiment's value

TECHNICAL IMPLEMENTATION

Platform: Google Colab with Python 3.10

Hardware: 4 CPU cores, 12 GB RAM

Libraries: pandas (data processing), scikit-learn (Random Forest), nltk and transformers (sentiment analysis), matplotlib (visualization)

Training Time: Under 20 minutes for full dataset

Reproducible: All experiments use open-source tools

RISK MANAGEMENT INNOVATIONS

Trailing 5% stop-loss prevents large single losses

Volatility circuit breakers halt trading during extreme market conditions

No single-day loss exceeded 5% of portfolio value

Full audit trail for regulatory compliance and transparency

RESEARCH CONTRIBUTIONS

First system to combine sentiment-conditioned Random Forest with dynamic trade sizing

Demonstrated 30% drawdown reduction through embedded risk controls

Proved sentiment analysis provides orthogonal value during market regime shifts

Created end-to-end pipeline from data ingestion to trade execution with compliance logging

LIMITATIONS ACKNOWLEDGED

English-language sentiment only (future: multilingual)

Daily data granularity (future: intraday)

Basic transaction cost modeling (future: market impact models)

Limited to Random Forest ensemble (future: transformer architectures)

PUBLICATION STATUS
Presented at 2nd International Conference on Intelligent Algorithms for Computational Intelligence Systems (IACIS 2025), Navkis College of Engineering, Hassan, August 22-23, 2025. Received Best Paper Presented award.

PRACTICAL IMPACT
This system demonstrates that AI can outperform traditional trading strategies when properly designed with sentiment integration and risk controls. The framework provides a foundation for deploying explainable, auditable AI in regulated financial markets while delivering superior risk-adjusted returns.
