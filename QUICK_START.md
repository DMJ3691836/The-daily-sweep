# Quick Start Guide - SNAP Daily Sweep

## Installation

1. Go to [TradingView](https://www.tradingview.com)
2. Open Pine Script Editor (Tools → Pine Script Editor)
3. Click "New" → "New indicator"
4. Copy the entire content of `snap_daily_sweep.pine` file
5. Paste it into the Pine Script editor
6. Click "Add to Chart"

---

## 5-Minute Setup

### Step 1: Load on Chart
- Open any chart (stocks, crypto, forex)
- Add the indicator from your favorites or search

### Step 2: Basic Configuration
- Go to Indicator Settings (click the gear icon)
- **Volume Sweep**: Keep default (Multiplier: 1.5)
- **Support & Resistance**: Keep default (Sensitivity: 0.5)
- **Momentum**: Keep default (RSI Length: 14)
- **Session**: Select your trading session (US/UK/ASIA)

### Step 3: Enable Alerts
- Click the bell icon on the indicator
- Select "Alert on all conditions"
- Choose notification method (email, push, SMS)

### Step 4: Start Trading
- Wait for green "BUY" labels
- Wait for red "SELL" labels
- Cross-check with your price action
- Enter when confirmed

---

## Dashboard Reading

The table in top-right shows:

| Field | What It Means |
|-------|---------------|
| Volume Status | HIGH ↑ = Unusual buying/selling | 
| RSI | 0-30 = Oversold (Buy opportunity) |
|  | 70-100 = Overbought (Sell opportunity) |
| Momentum | BULLISH ↑ = Price above moving average |
| Signal | BUY/SELL/WAIT = Current recommendation |
| Session | Active trading hours for your market |

---

## Example Scenarios

### Scenario 1: Buy Signal
```
Volume Status: HIGH ↑
RSI: 25 (Oversold)
Momentum: BULLISH ↑
Price: At support level
Signal: BUY ↑

Action: Enter long position with stop-loss below support
```

### Scenario 2: Sell Signal
```
Volume Status: HIGH ↑
RSI: 78 (Overbought)
Momentum: BEARISH ↓
Price: At resistance level
Signal: SELL ↓

Action: Enter short position with stop-loss above resistance
```

### Scenario 3: Wait Signal
```
Volume Status: Normal
RSI: 45 (Neutral)
Momentum: BULLISH ↑
Price: No clear support/resistance
Signal: WAIT

Action: Hold position or wait for clearer setup
```

---

## Default Colors Explained

- 🟢 **Green**: Buy signals, oversold, support levels, bullish momentum
- 🔴 **Red**: Sell signals, overbought, resistance levels, bearish momentum
- 🔵 **Blue**: Bullish momentum bars
- 🟠 **Orange**: Bearish momentum bars
- 🟣 **Purple**: Volume ratio indicator

---

## Tips for Best Results

✅ **Do:**
- Use on liquid markets (major stocks, crypto pairs, forex)
- Combine with price action analysis
- Follow the session filter for your market
- Use appropriate timeframes (5m-1D)
- Keep a trading journal

❌ **Don't:**
- Trade on illiquid assets
- Ignore risk management rules
- Expect 100% accuracy
- Over-optimize settings
- Trade against major trends without confluence

---

## Next Steps

1. **Paper Trade**: Test on your broker's simulator for 2 weeks
2. **Back-test**: Run historical tests with your settings
3. **Live Trade**: Start with 1 micro-lot and scale up
4. **Journal**: Record all trades and results
5. **Adjust**: Refine settings based on your results

---

For detailed documentation, see **INDICATOR_GUIDE.md**
