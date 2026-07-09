# SNAP Daily Sweep - Configuration Examples

This guide provides pre-configured settings for different trading styles and market conditions.

---

## 🔥 Strategy Profiles

### Profile 1: Conservative (Low Risk)

**Best for:** Risk-averse traders, long-term positions, institutional traders

```
VOLUME SWEEP SETTINGS:
  Enable Volume Sweep: ON
  Volume Lookback Period: 30
  Volume Multiplier: 2.0
  Volume Filter Type: EMA

SUPPORT & RESISTANCE:
  Enable S/R Detection: ON
  S/R Lookback Period: 100
  S/R Sensitivity: 0.3
  Detect Support: ON
  Detect Resistance: ON

MOMENTUM SETTINGS:
  Enable Momentum Analysis: ON
  Momentum RSI Length: 21
  RSI Overbought Level: 75
  RSI Oversold Level: 25

DISPLAY SETTINGS:
  Show Volume Alerts: ON
  Show S/R Lines: ON
  Show Momentum Color Coding: ON
  Bar Transparency: 70%

FILTER SETTINGS:
  Enable Timeframe Filter: ON
  Filter Timeframe: D (Daily)
  Enable Session Filter: ON
  Session Type: US
```

**Expected Results:**
- 10-15 signals per week on daily charts
- High win rate but fewer opportunities
- Best for portfolio managers

---

### Profile 2: Balanced (Moderate Risk)

**Best for:** Active traders, swing traders, medium-term positions

```
VOLUME SWEEP SETTINGS:
  Enable Volume Sweep: ON
  Volume Lookback Period: 20
  Volume Multiplier: 1.5
  Volume Filter Type: SMA

SUPPORT & RESISTANCE:
  Enable S/R Detection: ON
  S/R Lookback Period: 50
  S/R Sensitivity: 0.5
  Detect Support: ON
  Detect Resistance: ON

MOMENTUM SETTINGS:
  Enable Momentum Analysis: ON
  Momentum RSI Length: 14
  RSI Overbought Level: 70
  RSI Oversold Level: 30

DISPLAY SETTINGS:
  Show Volume Alerts: ON
  Show S/R Lines: ON
  Show Momentum Color Coding: ON
  Bar Transparency: 50%

FILTER SETTINGS:
  Enable Timeframe Filter: ON
  Filter Timeframe: 240 (4-Hour)
  Enable Session Filter: ON
  Session Type: US
```

**Expected Results:**
- 30-50 signals per week on 4H charts
- Balanced win rate and opportunities
- Standard recommended settings

---

### Profile 3: Aggressive (High Risk, High Reward)

**Best for:** Day traders, scalpers, experienced traders

```
VOLUME SWEEP SETTINGS:
  Enable Volume Sweep: ON
  Volume Lookback Period: 15
  Volume Multiplier: 1.2
  Volume Filter Type: SMA

SUPPORT & RESISTANCE:
  Enable S/R Detection: ON
  S/R Lookback Period: 30
  S/R Sensitivity: 0.8
  Detect Support: ON
  Detect Resistance: ON

MOMENTUM SETTINGS:
  Enable Momentum Analysis: ON
  Momentum RSI Length: 9
  RSI Overbought Level: 65
  RSI Oversold Level: 35

DISPLAY SETTINGS:
  Show Volume Alerts: ON
  Show S/R Lines: ON
  Show Momentum Color Coding: ON
  Bar Transparency: 30%

FILTER SETTINGS:
  Enable Timeframe Filter: ON
  Filter Timeframe: 60 (1-Hour)
  Enable Session Filter: ON
  Session Type: ALL
```

**Expected Results:**
- 50+ signals per day on 1H charts
- Lower win rate but rapid trading
- For experienced traders only

---

### Profile 4: Scalping (Very High Risk, Very High Frequency)

**Best for:** Professional scalpers, high-speed trading

```
VOLUME SWEEP SETTINGS:
  Enable Volume Sweep: ON
  Volume Lookback Period: 10
  Volume Multiplier: 1.1
  Volume Filter Type: Simple

SUPPORT & RESISTANCE:
  Enable S/R Detection: ON
  S/R Lookback Period: 20
  S/R Sensitivity: 1.0
  Detect Support: ON
  Detect Resistance: ON

MOMENTUM SETTINGS:
  Enable Momentum Analysis: ON
  Momentum RSI Length: 7
  RSI Overbought Level: 60
  RSI Oversold Level: 40

DISPLAY SETTINGS:
  Show Volume Alerts: ON
  Show S/R Lines: OFF
  Show Momentum Color Coding: ON
  Bar Transparency: 20%

FILTER SETTINGS:
  Enable Timeframe Filter: ON
  Filter Timeframe: 5 (5-Minute)
  Enable Session Filter: ON
  Session Type: US (Peak hours only)
```

**Expected Results:**
- 100+ signals per day on 5m charts
- Very high signal frequency
- Requires tight risk management

---

## 📈 Market Condition Profiles

### Trending Market (Strong momentum, directional bias)

```
Recommended: AGGRESSIVE Profile

Additional Adjustments:
  RSI Overbought: 75
  RSI Oversold: 25
  Volume Multiplier: 1.3
  S/R Sensitivity: 0.8
```

---

### Ranging Market (Choppy, sideways movement)

```
Recommended: CONSERVATIVE Profile

Additional Adjustments:
  Volume Multiplier: 2.5
  S/R Sensitivity: 0.8 (find consolidation levels)
  RSI Overbought: 70
  RSI Oversold: 30
  Momentum RSI Length: 21
```

---

### High Volatility Market (Explosive moves)

```
Recommended: BALANCED Profile

Additional Adjustments:
  Volume Multiplier: 1.8
  S/R Lookback: 30 (ignore old levels)
  RSI Length: 7 (faster response)
  Bar Transparency: 30%
```

---

### Low Volatility Market (Small moves, tight trading ranges)

```
Recommended: AGGRESSIVE Profile

Additional Adjustments:
  Volume Multiplier: 1.0 (any volume spike matters)
  S/R Lookback: 100 (use major levels)
  S/R Sensitivity: 0.2 (tight levels)
  Momentum RSI Length: 9
```

---

## 💰 Asset-Specific Profiles

### Stock Trading (SPY, QQQ, Individual Stocks)

```
VOLUME SWEEP SETTINGS:
  Volume Multiplier: 1.5
  Volume Lookback Period: 20
  Volume Filter Type: SMA

MOMENTUM SETTINGS:
  Momentum RSI Length: 14
  RSI Overbought: 70
  RSI Oversold: 30

FILTER SETTINGS:
  Session Type: US (9:30-16:00 EST)
  Filter Timeframe: 60 (1-Hour)
```

**Notes:** High volume thresholds due to varying daily volumes

---

### Crypto Trading (BTC, ETH, Alts)

```
VOLUME SWEEP SETTINGS:
  Volume Multiplier: 1.3
  Volume Lookback Period: 15
  Volume Filter Type: EMA

MOMENTUM SETTINGS:
  Momentum RSI Length: 9
  RSI Overbought: 65
  RSI Oversold: 35

FILTER SETTINGS:
  Session Type: ALL (24/7 market)
  Filter Timeframe: D (Daily) or 240 (4H)
```

**Notes:** Crypto is 24/7; lower RSI thresholds due to volatility

---

### Forex Trading (EUR/USD, GBP/USD, etc.)

```
VOLUME SWEEP SETTINGS:
  Volume Multiplier: 1.4
  Volume Lookback Period: 20
  Volume Filter Type: EMA

MOMENTUM SETTINGS:
  Momentum RSI Length: 14
  RSI Overbought: 70
  RSI Oversold: 30

FILTER SETTINGS:
  Session Type: UK (London Session, highest volume)
  Filter Timeframe: 240 (4-Hour)
```

**Notes:** Trade London and NY overlaps for best liquidity

---

### Futures Trading (ES, NQ, YM)

```
VOLUME SWEEP SETTINGS:
  Volume Multiplier: 1.2
  Volume Lookback Period: 20
  Volume Filter Type: SMA

MOMENTUM SETTINGS:
  Momentum RSI Length: 12
  RSI Overbought: 68
  RSI Oversold: 32

FILTER SETTINGS:
  Session Type: ALL
  Filter Timeframe: 60 (1-Hour)
```

**Notes:** Pre-market and after-hours opportunities; very liquid

---

## 🎯 Session-Based Profiles

### US Session Trader (9:30 AM - 4:00 PM EST)

```
Enable Session Filter: ON
Session Type: US
Volume Multiplier: 1.5
Filter Timeframe: 15 or 60
S/R Lookback: 50
Momentum RSI Length: 14
```

**Best for:** US stock and futures traders

---

### UK Session Trader (8:00 AM - 4:30 PM GMT)

```
Enable Session Filter: ON
Session Type: UK
Volume Multiplier: 1.5
Filter Timeframe: 60 or 240
S/R Lookback: 100
Momentum RSI Length: 21
```

**Best for:** Forex and UK stock traders

---

### Asia Session Trader (7:30 PM - 4:00 AM GMT)

```
Enable Session Filter: ON
Session Type: ASIA
Volume Multiplier: 1.8
Filter Timeframe: 240 or D
S/R Lookback: 100
Momentum RSI Length: 21
```

**Best for:** Forex, crypto, and Asia market traders

---

### Multi-Session Trader (All Sessions)

```
Enable Session Filter: OFF
Session Type: ALL
Volume Multiplier: 1.5
Filter Timeframe: D or 240
S/R Lookback: 50
Momentum RSI Length: 14
```

**Best for:** Swing traders, long-term positions

---

## 📊 Optimization Tips

1. **Start with Balanced Profile**
   - Use default settings for 1 week
   - Track win rate and signal frequency
   - Adjust one setting at a time

2. **Increase Volume Multiplier if:**
   - Too many false signals
   - Asset has consistent volume patterns
   - You want fewer, higher-quality signals

3. **Decrease Volume Multiplier if:**
   - Missing breakout trades
   - Asset has erratic volume
   - You want more trading opportunities

4. **Adjust S/R Sensitivity if:**
   - Levels too far from price (increase sensitivity)
   - Levels too close to price (decrease sensitivity)
   - Want major vs. minor levels

5. **Modify RSI Length if:**
   - Faster responses needed (lower length)
   - Smoother signals needed (higher length)
   - More false signals (increase length)

---

## 🔄 Testing Your Profile

Before live trading:

1. **Back-test** on 3-6 months of historical data
2. **Paper trade** for 1-2 weeks
3. **Track metrics:**
   - Win rate (%)
   - Average profit per win
   - Average loss per loss
   - Risk/reward ratio
   - Signal frequency

4. **Adjust** based on results
5. **Live trade** with 1 micro-lot minimum
6. **Scale up** only after consistent profitability

---

## 💾 Quick Reference

| Trading Style | Volume Mult | RSI Length | S/R Lookback | Best Timeframe |
|---------------|-------------|------------|--------------|----------------|
| Conservative | 2.0 | 21 | 100 | D |
| Balanced | 1.5 | 14 | 50 | 240 |
| Aggressive | 1.2 | 9 | 30 | 60 |
| Scalping | 1.1 | 7 | 20 | 5 |

---

## ⚠️ Risk Warning

These profiles are for educational purposes. Always:
- Use stop-losses
- Position size appropriately
- Practice on demo first
- Never risk more than you can afford to lose
- Consult a financial advisor

---

**Choose your profile, test it thoroughly, and trade with discipline! 🚀**
