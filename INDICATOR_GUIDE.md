# SNAP Daily Sweep - TradingView Indicator Guide

## Overview

SNAP Daily Sweep is a comprehensive TradingView indicator designed to identify volume sweeps, support/resistance levels, and momentum shifts across multiple market sessions. It combines volume analysis, momentum indicators, and price action detection to generate reliable trading signals.

---

## Features

### 1. **Volume Sweep Analysis**
- Detects abnormal volume spikes above or below average
- Configurable lookback period for volume averaging
- Multiple filtering methods (SMA, EMA, Simple Average)
- Customizable volume multiplier threshold
- Visual alerts for high and low volume events

### 2. **Support & Resistance Detection**
- Automatic identification of key price levels
- Adjustable sensitivity settings
- Independent toggle for support and resistance detection
- Dynamic calculation based on recent price action
- Visual line display on chart

### 3. **Momentum Analysis**
- RSI-based momentum detection
- Customizable overbought/oversold thresholds
- EMA-based trend confirmation
- Color-coded bar visualization
- Real-time momentum status display

### 4. **Multi-Session Filtering**
- US Trading Session (9:30 - 16:00 EST)
- UK Trading Session (8:00 - 16:30 GMT)
- Asia Trading Session (19:30 - 4:00 GMT)
- Optional all-session mode
- Prevents false signals during low-liquidity periods

### 5. **Signal Generation**
- **BUY Signal**: High volume + Oversold momentum + Price at support + Active session
- **SELL Signal**: High volume + Overbought momentum + Price at resistance + Active session
- Visual markers on chart with alert notifications
- Summary dashboard with real-time metrics

---

## Configuration Guide

### Volume Sweep Settings

| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| Enable Volume Sweep | ON | - | Toggle volume sweep analysis |
| Volume Lookback Period | 20 | 5-100 | Bars used to calculate average volume |
| Volume Multiplier | 1.5 | 0.5-5.0 | Threshold for volume spike detection |
| Volume Filter Type | SMA | SMA/EMA/Simple | Method for averaging volume |

**Tips:**
- Higher multiplier = fewer but stronger signals
- Lower lookback = more responsive to recent volume changes
- EMA gives more weight to recent volume bars

---

### Support & Resistance Settings

| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| Enable S/R Detection | ON | - | Toggle support/resistance detection |
| S/R Lookback Period | 50 | 10-200 | Bars analyzed for S/R levels |
| S/R Sensitivity | 0.5 | 0.1-2.0 | Sensitivity to detect levels |
| Detect Support | ON | - | Toggle support level detection |
| Detect Resistance | ON | - | Toggle resistance level detection |

**Tips:**
- Higher sensitivity = more levels detected
- Longer lookback = finds major structural levels
- Combine both support and resistance for balanced signals

---

### Momentum Settings

| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| Enable Momentum Analysis | ON | - | Toggle momentum detection |
| Momentum RSI Length | 14 | 5-50 | RSI calculation period |
| RSI Overbought Level | 70 | 50-99 | Threshold for overbought condition |
| RSI Oversold Level | 30 | 1-50 | Threshold for oversold condition |

**Tips:**
- Standard RSI uses 14-period (adjust for different timeframes)
- Lower RSI length = more sensitive to price changes
- Adjust thresholds based on asset volatility

---

### Display Settings

| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| Show Volume Alerts | ON | - | Display volume spike labels |
| Show S/R Lines | ON | - | Display support/resistance lines |
| Show Momentum Color Coding | ON | - | Color bars by momentum state |
| Bar Transparency | 50 | 0-100 | Transparency of bar coloring |

---

### Filter Settings

| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| Enable Timeframe Filter | ON | - | Filter by specific timeframe |
| Filter Timeframe | D | 5/15/60/240/D/W | Timeframe for filtering |
| Enable Session Filter | ON | - | Filter by trading session |
| Session Type | US | US/UK/ASIA/ALL | Active trading session |

**Session Times (UTC):**
- **US**: 14:00 - 21:00 (9:30 AM - 4:00 PM EST)
- **UK**: 08:00 - 16:30 (UTC time)
- **ASIA**: 19:30 - 04:00 (next day, UTC time)

---

## Understanding the Output

### Visual Elements

1. **Bar Colors**
   - 🔴 Red: Overbought momentum or bearish trend
   - 🟢 Green: Oversold momentum or bullish trend
   - 🔵 Blue: Bullish momentum
   - 🟠 Orange: Bearish momentum

2. **Labels on Chart**
   - ↑ Vol: High volume detected
   - ↓ Vol: Low volume detected
   - BUY (green): Strong buy signal
   - SELL (red): Strong sell signal

3. **Lines**
   - 🔴 Red Dashed: Resistance level
   - 🟢 Green Dashed: Support level

4. **Dashboard Table**
   - Top-right corner showing:
     - Volume Status (HIGH/LOW/Normal)
     - Current RSI value
     - Momentum direction
     - Active signal (BUY/SELL/WAIT)
     - Active session filter

### Plotted Indicators

- **Volume Ratio**: Purple line showing current volume ratio vs. average
- **RSI**: Blue line with overbought (70) and oversold (30) levels
- **Threshold Lines**: Visual reference for signal thresholds

---

## Trading Strategy Tips

### For Day Traders
- Use 5-minute or 15-minute timeframes
- Enable US session filter during market hours
- Lower volume multiplier (1.2-1.3) for more frequent signals
- Tight S/R sensitivity (0.3-0.5)

### For Swing Traders
- Use 4-hour or daily timeframes
- Disable or use ALL session filter
- Higher volume multiplier (1.8-2.0) for stronger signals
- Higher S/R sensitivity (0.8-1.2)

### For Scalpers
- Use 1-minute or 5-minute timeframes
- Enable all sections (volume, momentum, S/R)
- Lower RSI periods (9-12) for faster signals
- Tighter session windows for high liquidity

---

## Common Configurations

### Conservative Strategy
```
Volume Multiplier: 2.0
S/R Lookback: 100
RSI Length: 21
RSI Overbought: 75
RSI Oversold: 25
```

### Balanced Strategy
```
Volume Multiplier: 1.5
S/R Lookback: 50
RSI Length: 14
RSI Overbought: 70
RSI Oversold: 30
```

### Aggressive Strategy
```
Volume Multiplier: 1.2
S/R Lookback: 30
RSI Length: 9
RSI Overbought: 65
RSI Oversold: 35
```

---

## Alerts and Notifications

The indicator generates alerts for:
- **Strong BUY Signal**: "SNAP Sweep: Strong BUY Signal - Volume Surge + Oversold + Support Level"
- **Strong SELL Signal**: "SNAP Sweep: Strong SELL Signal - Volume Surge + Overbought + Resistance Level"

Enable alerts in TradingView to receive notifications on your device.

---

## Best Practices

1. **Combine with Price Action**: Use the indicator as a confirmation tool, not the sole trading signal
2. **Monitor Session Times**: Be aware of session transitions for better signal quality
3. **Adjust for Volatility**: In volatile markets, increase thresholds; in stable markets, decrease them
4. **Back-test Before Trading**: Test your configuration on historical data before live trading
5. **Use Risk Management**: Always use stop-losses and position sizing
6. **Update Regularly**: Review and adjust settings monthly based on market conditions

---

## Troubleshooting

### Too Many False Signals
- Increase volume multiplier
- Increase RSI periods
- Increase S/R lookback period
- Enable session filter

### Too Few Signals
- Decrease volume multiplier
- Decrease S/R lookback period
- Adjust overbought/oversold thresholds
- Use multiple timeframes

### Lines Not Showing
- Enable "Show S/R Lines" in Display Settings
- Ensure S/R Detection is enabled
- Check that support/resistance toggles are enabled

### Alerts Not Working
- Verify alerts are enabled in TradingView settings
- Check notification permissions on your device
- Ensure indicator is applied to active chart

---

## Version History

### v1.0 (2026)
- Initial release
- Volume sweep analysis
- Support/resistance detection
- Momentum analysis with RSI
- Multi-session filtering
- Visual dashboard and alerts

---

## Disclaimer

This indicator is provided for educational and informational purposes only. It should not be considered as financial advice. Always conduct your own research and consult with financial professionals before making trading decisions. Past performance does not guarantee future results.

---

## Support

For questions, feedback, or bug reports, please refer to the repository documentation or contact the development team.
