# Larry Williams VixFix

[Larry Williams VixFix](https://www.tradingview.com/script/TXPkMxfZ-Larry-Williams-VixFix/) measures how far price has moved from recent highs and lows over three lookbacks. Green background marks a potential bottom; red marks a potential top. Darker colour means more lookbacks agree. The method is described in [Williams’ VixFix note](https://www.ireallytrade.com/newsletters/VIXFix.pdf).

The indicator reprints. Act after the bar closes.

Buy values go negative when price stretches below recent lows. Sell values go positive when price stretches above recent highs.

## Inputs

| Parameter | Default | Notes |
|-----------|---------|-------|
| Length 1 / 2 / 3 | 22 / 66 / 132 | About one, three, and six months of trading days |

Stocks often use 22/66/132. Shorter lookbacks suit faster markets.

See [Installation](../README.md#installation) and [License](../README.md#license) in the repository readme. The legal disclaimer is in [DISCLAIMER.md](../DISCLAIMER.md).
