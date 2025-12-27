# Larry Williams VixFix Indicator

Larry Williams VixFix Indicator is a TradingView Pine Script indicator based on [Larry Williams' VixFix methodology](https://www.tradingview.com/script/TXPkMxfZ-Larry-Williams-VixFix/) that identifies potential market bottoms (buy signals) and tops (sell signals) through multi-timeframe volatility analysis approach with statistics tracking and customisable parameters. Important to note that this indicator reprints, therefore actions should be taken after bar close instead of during.

## 📋 Overview

![Larry William Vix Fix SPY sample chart](/media/larry-william-vix-fix-spy-sample.png)

The [Larry Williams VixFix](https://www.ireallytrade.com/newsletters/VIXFix.pdf) indicator measures price deviations from recent highs and lows over multiple timeframes to identify potential reversal points, especially for broad market index like SPY. Used in conjunction with VIX reading and the super trend indicator, can quite accurately pin the market bottoms (does not apply for market top).

## 📚 Table of Contents

- [📋 Overview](#-overview)
- [📊 Signal Interpretation & Recommended Actions](#-signal-interpretation--recommended-actions)
- [✨ Features](#-features)
- [🚀 Installation](#-installation)
- [⚙️ Configuration](#️-configuration)
- [🛠️ Troubleshooting](#️-troubleshooting)
- [⚠️ Important Notes](#️-important-notes)
- [⚠️ Disclaimer](#️-disclaimer)
- [📄 License](#-license)


## 📊 Signal Interpretation & Recommended Actions

### Signal Types
The indicator generates two types of signals with intensity-based visual feedback:

**🟢 Buy Signals** (Green background): Potential market bottom conditions
- Light Green: Single timeframe signal
- Medium Green: Two timeframes aligned
- Dark Green: All three timeframes aligned (strongest)

**🔴 Sell Signals** (Red background): Potential market top conditions
- Light Red: Single timeframe signal
- Medium Red: Two timeframes aligned
- Dark Red: All three timeframes aligned (strongest)

### How Signals Work
- **Buy Signals**: Generated when price deviates significantly below recent lows
- **Sell Signals**: Generated when price deviates significantly above recent highs
- **Signal Strength**: Determined by number of timeframes confirming the signal
- **Priority**: Longer timeframes override shorter ones to prevent conflicts

### Trading Recommendations

> **⚠️ IMPORTANT DISCLAIMER**: The following are educational examples only. Always implement proper risk management with stop losses and take profits. See [DISCLAIMER.md](../DISCLAIMER.md) for full legal disclaimers. The author is not liable for any trading decisions or outcomes.

#### 🟢 Buy Signal Activation
**Recommended Action**: Consider long positions or buying call options
- **Logic**: Market may be oversold and due for a bounce. Utilize VIX reading to identify where the market is at (dangerous ≥ 40), and super trend to gauge price reversal. Best case scenario is when Buy signals green, VIX reading > 40, super trend is red with new low.
- **Risk Management**: Depending on instrument, 10% for stocks, more for options and other leveraged instruments.
- **Take Profit**: Optional, can ride the wave until a reversal in super trend

#### 🔴 Sell Signal Activation
**Recommended Action**: I would personally recommend not to take action with the sell signal
- **Logic**: Markets naturally drift upwards, resulting in more new high then new lows, hence signalling a sell signal, meaning the signal is technically correct, but fundamentally inaccurate as there may be no reason for price to reverse.
- **Risk Management**: If a trade must be made, do cross reference with economic indicators and underlying fundamentals to justify the potential reversal
- **Take Profit**: NIL

#### 🌈 Multiple Timeframe Signals
**Recommended Action**: Increase position size with stronger conviction after checking VIX levels
- **Logic**: Higher probability when multiple timeframes align
- **Risk Management**: Use tighter stops with larger positions
- **Alternative**: Consider spread strategies to limit risk

### Risk Management Guidelines
- **Stop Losses**: Always use stops at logical levels
- **Position Sizing**: Never risk more than 1-2% of account per trade
- **Take Profits**: Set realistic targets based on historical performance
- **Time Limits**: Don't hold positions indefinitely without reassessment
- **Signal Quality**: Prioritize stronger multi-timeframe confirmations

### Trading Warnings
- **Not Financial Advice**: These are educational examples only
- **Individual Responsibility**: All trading decisions are your own
- **Risk Disclosure**: Trading involves substantial risk of loss
- **Professional Advice**: Consult licensed advisors for personalised guidance

## ✨ Features

### Core Functionality
- **Multi-Timeframe Analysis**: Three customisable lookback periods (22, 66, 132 days by default)
- **Dual Signal Detection**: Buy signals for market bottoms and sell signals for market tops
- **Hierarchical Priority**: Longer timeframes take precedence to prevent signal conflicts
- **Real-time Tracking**: Monitors signal effectiveness and trade outcomes
- **Statistical Analysis**: Tracks success rates and performance metrics over time

### Visual Elements & Customisation
- **Dynamic Background Colouring**: Signal intensity visualisation with colour depth
- **Layered Signal Lines**: Transparent lines for easy comparison across timeframes
- **Signal Strength Indicators**: More opaque lines indicate stronger signals
- **Flexible Table Display**: Show/hide statistics table for cleaner charts
- **Professional Precision**: All values rounded to 2 decimal places for clarity

### Advanced Analytics & Statistics
- **Trade Performance Tracking**: Win/loss ratios for both buy and sell signals
- **Configurable Duration**: Adjustable trade evaluation period (5-250 days)
- **Signal Frequency Analysis**: Percentage of total bars generating signals
- **Color-Coordinated Metrics**: Green for buy signals, red for sell signals
- **Mobile-Friendly**: Optional table hiding for mobile chart viewing

## 🚀 Installation

1. Open TradingView and navigate to the Pine Editor
2. Copy the contents of `larry-williams-vixfix-indicator`
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your desired settings in the indicator inputs

## ⚙️ Configuration

### Input Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| Length 1 | Integer | 22 | Short-term lookback period (1 month) |
| Length 2 | Integer | 66 | Medium-term lookback period (3 months) |
| Length 3 | Integer | 132 | Long-term lookback period (6 months) |
| Show Statistics Table | Boolean | true | Display/hide statistics table for mobile compatibility |
| Trade Duration (Days) | Integer | 30 | Days to wait before evaluating trade success (5-250) |

### Recommended Settings

**Stock Market**: 22/66/132 days, 30-day trade duration
**Forex**: 30/90/180 days, 20-40 day trade duration
**Crypto**: 14/42/84 days, 15-30 day trade duration

## 🛠️ Troubleshooting

### Common Issues

**No Signals Appearing:**
- Check that sufficient historical data is available (200+ bars)
- Verify lookback periods are appropriate for your timeframe
- Ensure market has sufficient volatility to generate signals

**Statistics Not Updating:**
- Confirm "Show Statistics Table" is enabled
- Verify trade duration setting is reasonable for your timeframe
- Check that trades have sufficient time to complete evaluation

**Background Colours Not Showing:**
- Verify background colours are enabled in TradingView settings
- Check that transparency levels allow visibility
- Ensure no other indicators are overriding background colours

## ⚠️ Important Notes

1. **Signal Interpretation**: Signals indicate potential reversal points, not guaranteed outcomes
2. **Market Context**: Always consider broader market conditions and fundamentals
3. **Backtesting**: Test on historical data before applying to live trading
4. **Multiple Confirmations**: Use with other technical indicators for best results
5. **Reprinting**: This indicator reprints, actions should be taken after bar close

## ⚠️ Disclaimer

This indicator is for educational and informational purposes only. It does not constitute financial advice. Trading involves risk, and past performance does not guarantee future results. Always conduct your own research and consider consulting with a financial advisor before making trading decisions.

## 📄 License

This project is licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/MPL/2.0/). See the [LICENSE](../LICENSE) file for details.
