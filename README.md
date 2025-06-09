# Intrinsic-Time-Trading

Overview
This coursework implements and backtests a mean reversion trading strategy based on intrinsic time conversion of tick-by-tick FX data. The strategy was tested on three EUR currency pairs: EUR/GBP, EUR/AUD, EUR/CAD, and EUR/CHF using 2023 M1 data.

The key takeaway is that the strategy's success is highly dependent on market volatility - achieving a remarkable +66.65% return on EUR/CHF (low volatility) while completely failing on EUR/AUD (high volatility) with a -100% loss.

Part 1: Strategy Development
Intrinsic Time Conversion
  Purpose: Convert "clock time" price data to "intrinsic time" based on significant price movements

Parameters:
  DELTA_UP: 0.00025 (threshold for up events)
  DELTA_DOWN: 0.00025 (threshold for down events)

Method: Tracks price movements and mode changes (up/down) to identify significant events

Trading Strategy Logic
  Mean Reversion Approach: Trades against recent price movements, expecting reversals

Entry Conditions:
  Long Position: After 3 consecutive down events with minimum movement of 0.0007
  Short Position: After 3 consecutive up events with minimum movement of 0.0007

Exit Conditions:
  Take Profit: After 7 events from entry
  Stop Loss: 5 consecutive events in opposite direction

Part 2: Backtesting Framework
Parameters Used
  Initial Capital: $10,000
  Position Size: 50% of current capital per trade
  Transaction Costs: 1.0 pip spread + $5 commission per trade
  Slippage: 0 pips (assumed high liquidity)


  
