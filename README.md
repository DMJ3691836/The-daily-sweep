# The Daily Sweep

A Pine Script v5 indicator for TradingView that automates the **Daily Sweep** futures trading methodology. It reads the daily chart bias, detects New York session fake-outs (sweeps), identifies aligned Fair Value Gaps, and marks pullback entry zones with a defined stop and target.

---

## How the Strategy Works

### Step 1 — Determine Daily Bias (Who's in Control?)
The indicator compares the last three completed daily candles:

| Structure | Bias | Direction | Target |
|-----------|------|-----------|--------|
| Higher Highs + Higher Lows | 🐂 Bullish | Long only | Previous Day High (PDH) |
| Lower Highs + Lower Lows | 🐻 Bearish | Short only | Previous Day Low (PDL) |
| Mixed | ◆ Neutral | No trade | — |

### Step 2 — Wait for the New York Session Sweep
During the configurable NY window (default **9:30 AM – 12:00 PM New York time**), the indicator watches for a **fake-out against the daily bias**:

- **Bullish day** → price wicks *below* the short-term swing low but *closes above* it (bear trap).
- **Bearish day** → price wicks *above* the short-term swing high but *closes below* it (bull trap).

This sweep is marked on the chart with a **"SWEEP ↑"** or **"SWEEP ↓"** label.

### Step 3 — Confirm an Aligned Fair Value Gap (FVG)
Within a configurable number of bars after the sweep, the indicator looks for a three-candle price imbalance (Fair Value Gap) that matches the daily bias:

- **Bullish FVG**: `high[2] < low[0]` — an upward gap confirming bullish momentum.
- **Bearish FVG**: `low[2] > high[0]` — a downward gap confirming bearish momentum.

A confirmed, aligned FVG is marked with **"FVG ✓"** and drawn as a shaded box on the chart.

### Step 4 — Enter on the Pullback
When price retraces back *into* the FVG box, an **"ENTRY →"** label fires. This is the precise, defined-risk entry point.

| Level | Bull Setup | Bear Setup |
|-------|-----------|-----------|
| **Entry** | Pullback into FVG box | Pullback into FVG box |
| **Stop** | 1 tick below sweep low | 1 tick above sweep high |
| **Target** | Previous Day High (PDH) | Previous Day Low (PDL) |

---

## Installation

1. Open [TradingView](https://www.tradingview.com) and navigate to the **Pine Script Editor** (bottom panel).
2. Copy the full contents of [`the_daily_sweep.pine`](./the_daily_sweep.pine).
3. Paste into the editor, click **Save**, then **Add to chart**.
4. Switch your chart to the **1-Hour timeframe**.

---

## Settings

### Daily Bias & Targets
| Setting | Default | Description |
|---------|---------|-------------|
| **Sweep Lookback (bars)** | 10 | Number of 1H bars defining the short-term swing high/low |
| **Show Daily Bias Label** | On | Displays the current bias and target price in the top-right corner |
| **Show PDH / PDL Target Lines** | On | Plots stepped horizontal lines at the previous day's high and low |

### New York Session
| Setting | Default | Description |
|---------|---------|-------------|
| **NY Sweep Window** | `0930-1200` | Time window (New York time) in which sweeps are monitored |
| **Mark Sweeps on Chart** | On | Labels sweep candles with an arrow |

### Fair Value Gap
| Setting | Default | Description |
|---------|---------|-------------|
| **Draw FVG Entry Boxes** | On | Shades the FVG zone with a coloured box |
| **FVG Box Width (bars)** | 50 | How far to the right the FVG box extends |
| **FVG Lookback After Sweep** | 5 | Max bars after a sweep in which an FVG must form to be valid |

### 🎯 NEW: Filters & Quality Control
| Setting | Default | Description |
|---------|---------|-------------|
| **Enable ATR Volatility Filter** | On | Only allows sweeps when volatility (ATR) is adequate. Filters noise in quiet conditions. |
| **Min ATR % of Price** | 0.3% | Minimum ATR as % of current price. Set 0 to disable. Higher = more selective. |

### 📊 NEW: Risk-Reward Analysis
| Setting | Default | Description |
|---------|---------|-------------|
| **Enable RR Filter** | On | Only show setups with risk-reward ratio above minimum threshold. |
| **Minimum RR Ratio** | 2.0 | Only show setups where reward/risk ≥ this ratio. 2.0 = 2:1 payoff. |
| **Show RR on Chart** | On | Display risk-reward ratio for active setups. |

### 📈 NEW: Interactive Dashboard
| Setting | Default | Description |
|---------|---------|-------------|
| **Enable Dashboard** | On | Show real-time setup status and key metrics. |
| **Dashboard Position** | top-left | Where to place the dashboard: top-left, top-right, bottom-left, or bottom-right. |

### 🔔 NEW: Enhanced Alerts
| Setting | Default | Description |
|---------|---------|-------------|
| **Use JSON-style Alert Messages** | Off | Format alerts with JSON-like structure for journaling/automation. |

### Visual
| Setting | Default | Description |
|---------|---------|-------------|
| **Bullish / Bearish Color** | Teal / Red | Colour scheme for all bullish and bearish elements |

---

## Alerts

Set up TradingView alerts using any of the built-in conditions:

| Alert Name | When It Fires |
|-----------|--------------|
| **Bullish Sweep Detected** | A bear-trap wick fires during the NY window on a bullish daily bias |
| **Bearish Sweep Detected** | A bull-trap wick fires during the NY window on a bearish daily bias |
| **Bullish FVG Aligned – Await Pullback** | A valid bullish FVG forms within the window after a bullish sweep |
| **Bearish FVG Aligned – Await Pullback** | A valid bearish FVG forms within the window after a bearish sweep |
| **Bullish Pullback Entry – Price in FVG** | Price first enters the bullish FVG zone (long entry signal) |
| **Bearish Pullback Entry – Price in FVG** | Price first enters the bearish FVG zone (short entry signal) |

---

## Chart Elements Reference

| Element | Description |
|---------|-------------|
| **Teal stepped line** | Previous Day High (PDH) — bull target |
| **Red stepped line** | Previous Day Low (PDL) — bear target |
| **Yellow background** | Active NY session window |
| **"SWEEP ↑/↓" label** | Sweep (fake-out) candle detected |
| **"FVG ✓" label** | Aligned Fair Value Gap confirmed |
| **"ENTRY →" label** | Price has pulled back into the FVG zone |
| **Shaded box (teal/red)** | FVG entry zone — valid until stop or target hit |
| **Dashed red line** | Stop-loss level (sweep extreme ± 1 tick) |
| **Bias label (top-right)** | Current daily bias and target level |
| **"RR: X.X" label** | Risk-reward ratio for active setup (mid-FVG) |
| **📈 Dashboard** | Real-time status: bias, session, setup state, entry/stop/target, RR ratio, ATR status, A+ checklist |

---

## 🆕 NEW: Smart Filters & Quality Metrics

### ATR Volatility Filter
The ATR filter prevents low-quality sweeps during quiet market conditions by measuring volatility:
- **Default**: Minimum 0.3% of price in 14-bar ATR
- **Benefit**: Avoids false sweeps and noisy price action
- **Configurable**: Adjust or disable entirely for different market conditions
- **Status**: Shown in dashboard as "✓ Vol OK" or "✗ Vol Low"

### Risk-Reward Analysis
Every setup is scored by its reward-to-risk ratio:
- **Calculation**: (Target − Entry) ÷ (Entry − Stop)
- **Default Minimum**: 2.0 (2:1 payoff)
- **Display**: Shown on chart and in dashboard for quick quality assessment
- **Filter**: Automatically suppresses low-RR setups (optional)

### A+ Checklist
The dashboard displays a live checklist of setup quality markers:
- ✓ **Sweep** — Confirmed fake-out during NY session
- ✓ **FVG** — Aligned Fair Value Gap detected
- ✓ **RR** — Reward-to-risk ratio meets threshold
- ✓ **Vol** — ATR volatility is adequate

---

## Dashboard Explained

The interactive dashboard (bottom-left by default) displays:
```
━━ DAILY SWEEP DASHBOARD ━━
[Status]  [Session]
Bias: [BIAS]  [Vol Status]
────────────────────────
Entry: [Price]
Stop: [Price]
Target: [Price]
RR: X.X:1
────────────────────────
A+ CHECKLIST:
Sweep: [✓/○]  FVG: [✓/○]  RR: [✓/○]  Vol: [✓/✗]
```

**Position options**: top-left, top-right, bottom-left, bottom-right (configurable)

---

## JSON Alert Messages (for Automation & Journaling)

Enable JSON-style alert messages to log structured setup data:

**Standard Alert Example (default):**
```
[Daily Sweep] Bearish fake-out (sweep below swing low) during NY session on a bullish daily bias. Watch for a bullish FVG.
```

**JSON Alert Example (optional):**
```json
{"event":"BULL_sweep","bias":"BULL","atr%":0.45,"volatility":"ADEQUATE"}
```

**Entry Alert with Full Details:**
```json
{"event":"BULL_entry","entry_zone":4825.50,"stop":4820.25,"target":4850.00,"rr":2.1}
```

Use JSON format with external tools, webhooks, or bots for automated journaling and position management.

---

## Notes

- **Recommended timeframe**: 1-Hour chart.
- The indicator uses `request.security` with `lookahead_on` to read confirmed daily bar data — this is intentional and does not introduce future-bar lookahead on completed candles.
- A neutral bias (◆) means the last three daily candles do not form a clean HH+HL or LH+LL sequence. No sweeps are flagged during neutral periods.
- The stop deactivates a setup when price *closes* beyond the stop level, keeping you in the trade through wicks.
- A setup is also deactivated once the target (PDH or PDL) is reached.

### About the New Features

**ATR Volatility Filter**
- Filters out sweeps during quiet market conditions
- Set "Min ATR % of Price" to 0 to disable the filter entirely
- Adjust higher (e.g., 0.5–0.7%) for more selective signals, or lower (e.g., 0.1–0.2%) for more signals
- ATR status shown in dashboard

**Risk-Reward Filter**
- Automatically calculates the RR ratio based on entry zone midpoint, stop, and target
- Disables setups with RR below the minimum threshold (2.0 by default)
- Overridable: turn off "Enable RR Filter" to see all FVG setups regardless of payoff
- RR ratio displayed on chart and in dashboard

**Interactive Dashboard**
- Auto-updates with current setup state, prices, and checklist status
- Can be repositioned to any of four corners
- Shows A+ checklist: sweep ✓, FVG ✓, RR ✓, volatility ✓
- Helps assess overall setup quality at a glance

**JSON Alert Messages** (NEW)
- Standard alerts remain human-readable and useful for manual trading
- Enable "Use JSON-style Alert Messages" to send structured data to external systems
- JSON format is ideal for bots, webhooks, or trading journals
- **Important**: This is NOT the same as TradingView webhooks (which must be configured in alert settings). This feature formats the alert message text for external parsing.
