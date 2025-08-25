# TradingView Scripts & Strategies

A collection of custom TradingView Pine Script™ indicators and strategies for technical analysis and algorithmic trading. This repository contains professionally developed tools with comprehensive documentation, statistics tracking, and risk management features.

## 📚 Table of Contents

- [TradingView Scripts \& Strategies](#tradingview-scripts--strategies)
  - [📚 Table of Contents](#-table-of-contents)
  - [📋 Overview](#-overview)
  - [📊 Available Indicators](#-available-indicators)
    - [All Moving Averages](#all-moving-averages)
    - [Opening Range Breakout (ORB)](#opening-range-breakout-orb)
    - [Larry Williams VixFix](#larry-williams-vixfix)
  - [🚀 Installation](#-installation)
  - [⚠️ Important Notes](#️-important-notes)
  - [🤝 Contributing](#-contributing)
  - [📄 License](#-license)

## 📋 Overview

This repository provides traders with advanced technical analysis tools designed for modern trading platforms. Each indicator includes comprehensive features such as customisable parameters, statistical analysis, visual feedback, and detailed documentation to support informed trading decisions.

## 📊 Available Indicators

### All Moving Averages
- **Path:** [All Moving Averages/](https://github.com/joveteo/trading-view-scripts/tree/main/All%20Moving%20Averages)
- **Description:**
  A comprehensive indicator featuring 14 different moving averages (SMA, EMA, WMA, HMA, VWMA, RMA, DEMA, TEMA, KAMA, ALMA, LSMA, TMA, ZLEMA) with multiple configurable lengths for each type.
  - User-friendly tooltips for each input
  - Unique colour for each MA type with progressively darker tones for higher lengths
  - Option to overlay on the main chart or display in a separate pane
  - Designed to help users bypass TradingView's indicator limit by combining many MAs in one script

### Opening Range Breakout (ORB)
- **Path:** [Opening Range Breakout/](https://github.com/joveteo/trading-view-scripts/tree/main/Opening%20Range%20Breakout)
- **Description:**
  A comprehensive indicator that identifies and tracks opening range breakouts with customisable duration, advanced statistics tracking, dynamic visual feedback, and session trend analysis.
  - Customisable opening range from 1 to 480 minutes
  - Dynamic range fill with colour-coded session status
  - Advanced breakout logic with first-signal priority
  - Session trend indicators (SMA, EMA, RMA, WMA, Anchor VWAP)
  - Customisable statistics table with colour coordination

### Larry Williams VixFix
- **Path:** [Larry Williams VixFix/](https://github.com/joveteo/trading-view-scripts/tree/main/Larry%20Williams%20VixFix)
- **Description:**
  An implementation of the Larry Williams VixFix indicator for identifying market bottoms and tops through multi-timeframe volatility analysis.
  - Configurable lengths for buy and sell signals (default 22, 66, 132 days)
  - Dynamic background colouring with intensity-based visual feedback
  - Statistical analysis with performance tracking
  - Mobile-friendly table display options
  - Educational trading recommendations with risk management guidelines

## 🚀 Installation

1. Open TradingView and navigate to the Pine Editor
2. Copy the complete script code from the desired indicator folder
3. Paste into the Pine Editor
4. Click "Add to Chart"
5. Configure your preferred settings in the indicator inputs

## ⚠️ Important Notes

- **Educational Purpose**: All tools are for educational and informational purposes only
- **No Financial Advice**: These indicators do not constitute financial advice
- **Risk Management**: Always implement proper risk management with stop losses and position sizing
- **Backtesting**: Test on historical data before applying to live trading
- **Disclaimer**: See [DISCLAIMER.md](DISCLAIMER.md) for full legal disclaimer

## 🤝 Contributing

Contributions, suggestions, and improvements are welcome! Please:
- Open an issue for bug reports or feature requests
- Submit a pull request for code contributions
- Follow the existing code style and documentation standards

## 📄 License

This repository is licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/MPL/2.0/). See the [LICENSE](LICENSE) file for details.
