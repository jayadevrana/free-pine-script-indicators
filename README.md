# Free Pine Script Indicators & Strategies (TradingView, Pine Script v6)

Free, open-source **TradingView Pine Script v6** indicators and strategies from my YouTube lessons, with chart snapshots and honest backtests (costs included).
Every script compiles cleanly in Pine Script v6; signal logic is non-repainting.

**Copy-paste pages with snapshots:** https://jayadevrana.in/free-pine-script-indicators/
**YouTube:** [@jayadevranaalgo](https://www.youtube.com/@jayadevranaalgo)

| Script | Type | What it does | Code | Video |
|---|---|---|---|---|
| **EMA Trend Signals** | Indicator (Overlay) | Fast/slow EMA crossover signals filtered by a 200 EMA trend line, with a trend-coloured fill, non-repainting BUY/SELL labels and alert conditions. | [scripts/ema-trend-signals.pine.txt](scripts/ema-trend-signals.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/ema-trend-signals/) | [▶ Watch](https://youtu.be/dRnKEIgOgPs) |
| **RSI Zones** | Indicator (Separate pane) | A clean RSI in its own pane with 70/30 levels and a background that turns red when overbought and teal when oversold. | [scripts/rsi-zones.pine.txt](scripts/rsi-zones.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/rsi-zones/) | [▶ Watch](https://youtu.be/hWeaFBH0lbk) |
| **EMA Trend Strategy** | Strategy (Overlay + Strategy Tester) | The EMA trend idea as a backtestable strategy: realistic commission and slippage, ATR stop-loss and take-profit, and JSON alert messages ready for webhook automation. | [scripts/ema-trend-strategy.pine.txt](scripts/ema-trend-strategy.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/ema-trend-strategy/) | [▶ Watch](https://youtu.be/hWeaFBH0lbk) |
| **Simple Trend Painter** | Indicator (Overlay) | A beginner-friendly first indicator: candles painted green above a moving average and red below it, an orange dot on unusually busy candles, and an alert when price crosses the average. | [scripts/simple-trend-painter.pine.txt](scripts/simple-trend-painter.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/simple-trend-painter/) | [▶ Watch](https://youtu.be/cgh8KTgHsJE) |
| **Previous Day Levels** | Indicator (Overlay) | Yesterday's high and low drawn automatically on any chart and timeframe, with the range shaded, breakout markers and alerts. Non-repainting: it reads the previous completed daily candle. | [scripts/previous-day-levels.pine.txt](scripts/previous-day-levels.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/previous-day-levels/) | [▶ Watch](https://youtu.be/6k3FyYfuaAI) |
| **Engulfing Candles** | Indicator (Overlay) | Finds bullish and bearish engulfing candles automatically, labels them BULL and BEAR, paints the candle itself, and sends alerts. A body-size ratio filters out the weak patterns. | [scripts/engulfing-candles.pine.txt](scripts/engulfing-candles.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/engulfing-candles/) | [▶ Watch](https://youtu.be/NsH5iIXTcFU) |
| **My First Strategy** | Strategy (Overlay) | A beginner strategy for learning the Strategy Tester: buy when price closes back above a trend average, then a 2% stop loss and a 4% take profit. Commission and slippage are included, so the back test is honest. | [scripts/first-strategy.pine.txt](scripts/first-strategy.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/first-strategy/) | [▶ Watch](https://youtu.be/at8brpnawyE) |
| **Trend Dashboard** | Indicator (Overlay) | A small table in the corner of the chart showing whether price is above or below its trend average on three timeframes at once. Every timeframe is a setting, so you can match it to how you trade. | [scripts/trend-dashboard.pine.txt](scripts/trend-dashboard.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/trend-dashboard/) | [▶ Watch](https://youtu.be/7PgWNFcVHmo) |
| **Pivot Levels** | Indicator (Overlay) | Support and resistance drawn by the code: it finds pivot highs and lows, draws each level as a line that stretches forward with price, and alerts you when the newest level breaks. | [scripts/pivot-levels.pine.txt](scripts/pivot-levels.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/pivot-levels/) | [▶ Watch](https://youtu.be/lwA9H_CYzbA) |
| **Session Filter** | Indicator (Overlay) | Shades your trading hours on the chart and keeps signals only inside them. Every signal the filter removed is marked with a grey cross, so you can see exactly what it cost you. | [scripts/session-filter.pine.txt](scripts/session-filter.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/session-filter/) | [▶ Watch](https://youtu.be/DT3yRTlD7U8) |
| **Risk Managed Strategy** | Strategy (Overlay) | An ATR stop and a position size calculated from the risk you choose, so every loss costs the same. The back test result is honestly negative, and the lesson explains exactly why. | [scripts/risk-strategy.pine.txt](scripts/risk-strategy.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/risk-strategy/) | [▶ Watch](https://youtu.be/MXxL8ZLBYms) |
| **Mini Screener** | Indicator (Overlay) | One table on one chart that watches five markets at once: price, change since the last candle, and whether each one is above its trend average. Built with arrays and a loop. | [scripts/mini-screener.pine.txt](scripts/mini-screener.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/mini-screener/) | [▶ Watch](https://youtu.be/5u6-1ko4iqs) |
| **Alerts & Automation** | Indicator (Overlay) | Both ways Pine Script raises an alert, side by side: a readable message for your phone, and a JSON message for a webhook, which is the first real step towards automated trading. | [scripts/alerts-automation.pine.txt](scripts/alerts-automation.pine.txt) · [page](https://jayadevrana.in/free-pine-script-indicators/alerts-automation/) | [▶ Watch](https://youtu.be/pvDtQ_6nkig) |

## EMA Trend Signals
![EMA Trend Signals on a TradingView chart](images/ema-signals-chart.jpg)

Fast/slow EMA crossover signals filtered by a 200 EMA trend line, with a trend-coloured fill, non-repainting BUY/SELL labels and alert conditions.

- Signals print only after the candle closes (barstate.isconfirmed), so they do not repaint.
- BUY needs a fast-over-slow EMA cross while price is above the Trend EMA; SELL is the mirror image.
- Create an alert on "EMA Trend Signals" and pick Buy or Sell, set to Once Per Bar Close.

## RSI Zones
![RSI Zones on a TradingView chart](images/rsi-zones-chart.jpg)

A clean RSI in its own pane with 70/30 levels and a background that turns red when overbought and teal when oversold.

- overlay = false puts the RSI in its own pane under the price chart.
- The background shading uses a nested ternary: red above 70, teal below 30, no colour (na) otherwise.
- Change the RSI length in the indicator settings; 14 is the classic default.

## EMA Trend Strategy
![EMA Trend Strategy on a TradingView chart](images/strategy-tester.jpg)

The EMA trend idea as a backtestable strategy: realistic commission and slippage, ATR stop-loss and take-profit, and JSON alert messages ready for webhook automation.

- Honest result: about +$298 before costs, but ~$411 of commission turned it into a -$112 loss. Test costs before you trust any backtest.
- Each trade risks 2 ATR (stop) to make 3 ATR (target), sized at 10% of equity.
- For automation, create a strategy alert and put {{strategy.order.alert_message}} in the message box; your webhook receives {"side":"buy","symbol":"SPX500USD"}.

## Simple Trend Painter
![Simple Trend Painter on a TradingView chart](images/simple-trend-painter-chart.jpg)

A beginner-friendly first indicator: candles painted green above a moving average and red below it, an orange dot on unusually busy candles, and an alert when price crosses the average.

- barcolor paints every candle green when the close is above the moving average and red when it is below.
- An orange circle marks candles whose volume is more than twice the 20-candle average volume.
- Create an alert on "Simple Trend Painter" and pick "Price crossed average".

## Previous Day Levels
![Previous Day Levels on a TradingView chart](images/previous-day-levels-chart.jpg)

Yesterday's high and low drawn automatically on any chart and timeframe, with the range shaded, breakout markers and alerts. Non-repainting: it reads the previous completed daily candle.

- request.security reads high[1] and low[1] from the daily timeframe, so the levels are yesterday's finished values.
- lookahead is only safe here because of the [1]: the script never uses data from an unfinished day.
- Create an alert on "Previous Day Levels" and pick "Broke yesterday's high" or "Broke yesterday's low".

## Engulfing Candles
![Engulfing Candles on a TradingView chart](images/engulfing-candles-chart.jpg)

Finds bullish and bearish engulfing candles automatically, labels them BULL and BEAR, paints the candle itself, and sends alerts. A body-size ratio filters out the weak patterns.

- A bullish engulfing needs a red candle followed by a green body that covers it, and is bigger by the ratio you set.
- math.abs measures each body, so the comparison ignores the direction of the candle.
- Create an alert on "Engulfing Candles" and pick "Bullish engulfing" or "Bearish engulfing".

## My First Strategy
![My First Strategy on a TradingView chart](images/first-strategy-chart.jpg)

A beginner strategy for learning the Strategy Tester: buy when price closes back above a trend average, then a 2% stop loss and a 4% take profit. Commission and slippage are included, so the back test is honest.

- strategy() sets 10,000 starting capital, 10% of equity per trade, 0.05% commission and 2 ticks of slippage.
- strategy.entry buys on a close back above the trend average, but only when no position is open.
- strategy.exit places the stop and target together; whichever price is hit first closes the trade.

## Trend Dashboard
![Trend Dashboard on a TradingView chart](images/trend-dashboard-chart.jpg)

A small table in the corner of the chart showing whether price is above or below its trend average on three timeframes at once. Every timeframe is a setting, so you can match it to how you trade.

- A small trendUp() function asks one question: is the close above its EMA?
- request.security runs that same function on each of the three timeframes you choose.
- table.new with var creates the table once, and barstate.islast fills it in on the newest candle only.

## Pivot Levels
![Pivot Levels on a TradingView chart](images/pivot-levels-chart.jpg)

Support and resistance drawn by the code: it finds pivot highs and lows, draws each level as a line that stretches forward with price, and alerts you when the newest level breaks.

- ta.pivothigh and ta.pivotlow find a candle that is higher (or lower) than the chosen number of candles on both sides.
- A level is only confirmed after the right-hand candles exist, so it appears a few candles late. That is honest, not a bug.
- line.set_x2 stretches the newest support and resistance to the current candle on every bar.

## Session Filter
![Session Filter on a TradingView chart](images/session-filter-chart.jpg)

Shades your trading hours on the chart and keeps signals only inside them. Every signal the filter removed is marked with a grey cross, so you can see exactly what it cost you.

- time() returns na outside the session, so not na(time(...)) is true only inside your hours.
- bgcolor shades those hours; na means paint nothing at all.
- buySignal = rawBuy and inSession. That single "and" is the whole filter.

## Risk Managed Strategy
![Risk Managed Strategy on a TradingView chart](images/risk-strategy-chart.jpg)

An ATR stop and a position size calculated from the risk you choose, so every loss costs the same. The back test result is honestly negative, and the lesson explains exactly why.

- stopDist = ATR x multiplier, so the stop fits how far price is actually moving today.
- qty = math.min(riskCash / stopDist, equity / close): every loss costs the same, and the size never exceeds what the account can fund.
- A tighter stop means more trades (199 in lesson 5 became 504 here), and every extra trade pays commission and slippage.

## Mini Screener
![Mini Screener on a TradingView chart](images/mini-screener-chart.jpg)

One table on one chart that watches five markets at once: price, change since the last candle, and whether each one is above its trend average. Built with arrays and a loop.

- One small function returns three answers in a bag: [close, change, above trend].
- request.security runs that function on each symbol you pick, so each call carries three values instead of one.
- array.from stores the answers and a for loop fills every row, so adding markets does not mean adding code.

## Alerts & Automation
![Alerts & Automation on a TradingView chart](images/alerts-automation-chart.jpg)

Both ways Pine Script raises an alert, side by side: a readable message for your phone, and a JSON message for a webhook, which is the first real step towards automated trading.

- alertcondition() adds an entry to the alert menu. alert() fires from inside the code and can build the message while the script runs.
- barstate.isconfirmed means the alert only fires on a finished candle, so a signal cannot vanish after it fires.
- The JSON message is plain text in a shape a program can read: send it to a webhook and your own program places the order.

## How to use
1. In TradingView open the **Pine Editor**, create a new indicator (or strategy for strategy files).
2. Paste the contents of the `.pine.txt` file and click **Add to chart**.

## Custom work
Need a custom Pine Script indicator/strategy, an MQL5 EA, or a TradingView-to-broker bridge? → https://jayadevrana.in/

## License
[Mozilla Public License 2.0](LICENSE) (the TradingView open-source default). Educational content only — **not financial advice**. Past performance does not predict future results.

---
Keywords: pine script v6, pine script course, pine script tutorial, tradingview indicator, free tradingview indicators, pine script strategy, non repainting indicator, tradingview alerts, backtesting, algo trading
