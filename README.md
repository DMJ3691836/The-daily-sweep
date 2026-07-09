# The Daily Sweep - SNAP Daily Sweep Indicator

## 📊 Overview

**SNAP Daily Sweep** is a professional-grade TradingView indicator designed to identify volume sweeps, support/resistance levels, and momentum shifts across multiple market sessions. It combines advanced volume analysis, momentum indicators, and price action detection to generate reliable trading signals for day traders, swing traders, and scalpers.

### Key Features

✅ **Volume Sweep Analysis** - Detect abnormal volume spikes with customizable multipliers
✅ **Smart S/R Detection** - Automatic support and resistance level identification
✅ **Momentum Indicators** - RSI-based overbought/oversold detection with EMA confirmation
✅ **Multi-Session Filtering** - US, UK, Asia, and all-session modes
✅ **Visual Dashboard** - Real-time metrics in an on-chart table
✅ **Configurable Sections** - Customize every parameter for your strategy
✅ **Alert System** - Get notified on buy/sell signals

---

## 🚀 Quick Start

### Installation
1. Copy the content of `snap_daily_sweep.pine`
2. Open TradingView → Pine Script Editor
3. Create new indicator and paste the code
4. Click "Add to Chart"

### First 5 Minutes
1. Open any liquid chart (stocks, crypto, forex)
2. Add the indicator
3. Go to Settings → Select your trading session (US/UK/ASIA)
4. Enable alerts (bell icon)
5. Wait for BUY/SELL signals

👉 **See [QUICK_START.md](QUICK_START.md) for detailed setup instructions**

---

## 📈 How It Works

### Buy Signal Generation
```
High Volume + Oversold Momentum + Price at Support + Active Session = BUY ✅
```

### Sell Signal Generation
```
High Volume + Overbought Momentum + Price at Resistance + Active Session = SELL ❌
```

---

## ⚙️ Configuration Sections

### 1. **Volume Sweep Settings**
- Enable/disable volume analysis
- Lookback period (5-100 bars)
- Volume multiplier (0.5-5.0x)
- Filter type: SMA, EMA, or Simple Average

### 2. **Support & Resistance Settings**
- Enable/disable S/R detection
- Lookback period (10-200 bars)
- Sensitivity adjustment (0.1-2.0)
- Toggle support/resistance independently

### 3. **Momentum Settings**
- RSI calculation period (5-50)
- Overbought threshold (50-99)
- Oversold threshold (1-50)
- Enable/disable momentum analysis

### 4. **Display Settings**
- Show/hide volume alerts
- Show/hide S/R lines
- Momentum color coding
- Transparency control (0-100%)

### 5. **Filter Settings**
- Timeframe filter (5m, 15m, 1h, 4h, D, W)
- Session type (US, UK, ASIA, ALL)
- Enable/disable filters

---

## 📊 Dashboard Explained

The on-chart table displays:

| Metric | Values | Meaning |
|--------|--------|---------|
| **Volume Status** | HIGH ↑ / LOW ↓ / Normal | Current volume level |
| **RSI** | 0-100 | Momentum strength (30=oversold, 70=overbought) |
| **Momentum** | BULLISH ↑ / BEARISH ↓ | Price vs EMA direction |
| **Signal** | BUY ↑ / SELL ↓ / WAIT | Current trade signal |
| **Session** | US / UK / ASIA / ALL | Active trading session |

---

## 🎯 Use Cases

### Day Trading (5m - 1h charts)
- High volume multiplier (1.8-2.0) for strong signals
- US session filter for tight bid-ask spreads
- Tight S/R sensitivity for quick entries/exits

### Swing Trading (4h - D charts)
- Balanced multiplier (1.5)
- No session filter for more opportunities
- Wider S/R sensitivity for major levels

### Scalping (1m - 5m charts)
- Low volume multiplier (1.2-1.3)
- Tight session windows
- Short RSI period (9-12)

---

## 📋 Trading Session Times (UTC)

- **🇺🇸 US Session**: 14:00 - 21:00 (9:30 AM - 4:00 PM EST)
- **🇬🇧 UK Session**: 08:00 - 16:30 (London time)
- **🌏 Asia Session**: 19:30 - 04:00 (Tokyo/Sydney times)

---

## 📚 Documentation

- **[QUICK_START.md](QUICK_START.md)** - 5-minute setup and basics
- **[INDICATOR_GUIDE.md](INDICATOR_GUIDE.md)** - Comprehensive documentation
  - Configuration guide
  - Signal generation explained
  - Trading strategy tips
  - Common configurations
  - Troubleshooting guide

---

## 🎨 Visual Elements

### Colors
- 🟢 **Green**: Buy signals, oversold, support, bullish
- 🔴 **Red**: Sell signals, overbought, resistance, bearish
- 🔵 **Blue**: Bullish momentum
- 🟠 **Orange**: Bearish momentum
- 🟣 **Purple**: Volume ratio

### Chart Labels
- **↑ Vol**: High volume detected
- **↓ Vol**: Low volume detected
- **BUY**: Strong buy signal
- **SELL**: Strong sell signal

### Lines
- 🔴 **Red Dashed**: Resistance level
- 🟢 **Green Dashed**: Support level

---

## 💡 Best Practices

✅ Combine with price action analysis
✅ Use on liquid markets only
✅ Follow the session filter for your market
✅ Always use stop-losses
✅ Back-test before live trading
✅ Keep a trading journal
✅ Adjust settings monthly

❌ Don't trade illiquid assets
❌ Don't ignore risk management
❌ Don't expect 100% accuracy
❌ Don't over-optimize settings
❌ Don't trade against major trends

---

## 📊 Example Signals

### Perfect Buy Setup
```
✅ Volume: HIGH ↑
✅ RSI: 25 (Oversold)
✅ Momentum: BULLISH ↑
✅ Price: At support level
✅ Signal: BUY
```

### Perfect Sell Setup
```
✅ Volume: HIGH ↑
✅ RSI: 78 (Overbought)
✅ Momentum: BEARISH ↓
✅ Price: At resistance level
✅ Signal: SELL
```

---

## ⚠️ Disclaimer

This indicator is provided for educational purposes only. It is not financial advice. Past performance does not guarantee future results. Always conduct your own research and consult financial professionals before trading.

---

## 📝 Version

**SNAP Daily Sweep v1.0**

---

## 🤝 Contributing

Found a bug or have a suggestion? Please contribute to improve the indicator!

---

## 📄 License

See LICENSE file for details.

---

**Happy Trading! 🚀📈**
