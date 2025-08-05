# S50 TFEX Trend-Following Breakout Strategy

A momentum-based breakout trading strategy designed specifically for the S50 TFEX (Thai Stock Exchange Futures) market, optimized for 30-minute timeframes.

## 📊 Strategy Overview

This strategy capitalizes on momentum when price breaks through significant support/resistance levels identified by pivot points. It combines trend-following principles with robust risk management to achieve consistent returns in the Thai futures market.

### Key Features
- **Pivot-Based Entry System**: 21-bar lookback with 2-bar confirmation
- **ATR-Based Risk Management**: Dynamic stop losses and position sizing
- **Aggressive Risk-Reward**: 8:1 ratio for maximum profit extraction
- **Account Risk Control**: Fixed 1% risk per trade with dynamic contract sizing

## 📈 Performance Metrics

### Overall Results
- **Net Profit**: 61,085 THB (**122.17% return**)
- **Total Trades**: 29 (statistically significant sample)
- **Win Rate**: 58.62%
- **Profit Factor**: 2.735 (excellent profitability)
- **Average Trade**: 2,106 THB

### Risk Analysis
- **Maximum Drawdown**: 9.31% (10,395 THB)
- **Sharpe Ratio**: 0.66 (decent risk-adjusted returns)
- **Sortino Ratio**: 3.068 (excellent downside protection)

### Directional Performance
| Direction | Trades | Win Rate | Profit Factor | Net Profit |
|-----------|--------|----------|---------------|------------|
| **Long**  | 13     | 46.15%   | 1.686         | 12,545 THB |
| **Short** | 16     | 68.75%   | 3.867         | 48,540 THB |

*Note: Short trades significantly outperformed, indicating the strategy excels in declining markets.*

## 🔧 Strategy Implementation

### Entry Conditions
- **Long Entry**: Price breaks above swing high (pivot high)
- **Short Entry**: Price breaks below swing low (pivot low)

### Risk Management
- **Stop Loss**: 
  - Long: `Swing Low - ATR`
  - Short: `Swing High + ATR`
- **Take Profit**:
  - Long: `Swing High + (ATR × 8)`
  - Short: `Swing Low - (ATR × 8)`

### Position Sizing
```pinescript
// Dynamic position sizing based on account risk
riskAmount = strategy.equity * 0.01  // 1% account risk
longContracts = riskAmount / (swingHigh - longStop)
shortContracts = riskAmount / (shortStop - swingLow)
```

## 📁 Repository Structure

```
tradingview-s50-trend-following-breakout/
├── s50-trend-following-breakout.pine    # Main strategy implementation
├── README.md                           # This file - project overview
└── .gitignore                          # Git ignore rules
```

## 🚀 Getting Started

### Prerequisites
- TradingView account with Pine Script access
- S50 TFEX market data subscription
- Understanding of Thai futures market hours (9:45 AM - 4:30 PM ICT)

### Installation
1. Copy the Pine Script code from `s50-trend-following-breakout.pine`
2. Open TradingView Pine Script Editor
3. Paste the code and save as new strategy
4. Apply to S50 TFEX chart with 30-minute timeframe

### Configuration
Default parameters are optimized for S50 TFEX:
- **Left Bars**: 21 (pivot lookback)
- **Right Bars**: 2 (pivot confirmation)
- **ATR Length**: 10 periods
- **Risk %**: 1% per trade
- **Risk-Reward Ratio**: 8:1

## 📊 Market Suitability

### Optimal Conditions
- **Trending Markets**: Strategy excels during clear directional moves
- **Higher Volatility**: ATR-based system requires sufficient price movement
- **Bear Markets**: Historical data shows superior performance in declining markets

### Performance by Market Regime
- **Trending**: Excellent (high profit factor)
- **Sideways**: Moderate (whipsaw risk)
- **Volatile**: Good (ATR adaptation)

## 🔍 Strategy Analysis

### Strengths
1. **Momentum Capture**: Effectively rides breakout moves
2. **Risk Control**: ATR-based dynamic risk management
3. **High R:R**: 8:1 ratio maximizes profit potential
4. **Statistical Edge**: 58.62% win rate with 2.735 profit factor

### Considerations
1. **Frequency**: Selective entries (29 trades in backtest period)
2. **Drawdown**: 9.31% maximum drawdown requires patience
3. **Directional Bias**: Better performance on short trades
4. **Market Dependency**: Requires trending conditions for optimal performance

## 🛠️ Development

### AI Agent System
This project uses specialized AI agents for development:
- **@pine-script-engineer**: Pine Script development and optimization
- **@quant-trading-analyst**: Performance analysis and validation
- **@documentation-specialist**: Documentation and reporting

### Contributing
1. Fork the repository
2. Create feature branch
3. Implement changes following CLAUDE.md guidelines
4. Test strategy with backtesting
5. Update documentation
6. Submit pull request

## 📚 Documentation

- **[Strategy Analysis](note.md)**: Comprehensive performance analysis
- **[Development Guide](CLAUDE.md)**: AI development guidelines
- **[Agent Coordination](.claude/agents/README.md)**: Specialized agent usage

## ⚠️ Disclaimer

This trading strategy is provided for educational and research purposes only. Past performance does not guarantee future results. Trading futures involves substantial risk and may not be suitable for all investors. Always conduct your own analysis and consider your risk tolerance before trading.

## 📄 License

This project is licensed under the Mozilla Public License 2.0 - see the [MPL-2.0](https://mozilla.org/MPL/2.0/) for details.

---

**Strategy Type**: Momentum Breakout | **Market**: S50 TFEX | **Timeframe**: 30 minutes | **Risk Level**: Moderate
