
<p align="center">
  <img src="https://avatars.githubusercontent.com/u/209633456?v=4" width="160" alt="RedTail Indicators Logo"/>
</p>

<h1 align="center">RedTail Volume Profile</h1>

<p align="center">
  <b>A comprehensive volume profile indicator for NinjaTrader 8 with institutional-grade features.</b><br>
  Nearly 10,000 lines of NinjaScript — this is not a basic volume profile.
</p>

<p align="center">
  <a href="https://buymeacoffee.com/dmwyzlxstj">
    <img src="https://img.shields.io/badge/☕_Buy_Me_a_Coffee-FFDD00?style=flat-square&logo=buy-me-a-coffee&logoColor=black" alt="Buy Me a Coffee"/>
  </a>
</p>

---

## Overview

RedTail Volume Profile is a full-featured volume profile analysis suite designed for serious futures traders. It covers every angle of volume profile analysis — from session-based profiles to composite ranges, naked level tracking, overnight sessions, candle-level profiles, and even experimental move detection — all in a single indicator with full visual customization.

---

## Profile Modes

- **Session** — Per-session profiles with configurable lookback depth. Optional custom session start/end times (e.g., 0930–1600) to isolate RTH or any window you want.
- **Visible Range** — Dynamically calculates the profile across your visible chart area, updating as you scroll and zoom.
- **Weekly** — Weekly volume profiles with configurable weeks lookback.
- **Monthly** — Monthly volume profiles with configurable months lookback.
- **Composite** — Aggregate volume profiles across custom date ranges. Supports Days Back, Weeks Back, Months Back, or a Custom Start/End Date range.
- **Anchored** — Session-by-session profiles pinned to their respective time periods, each rendered independently.

**Profile Alignment:** Left, Right, or Anchored to session open.

---

## Point of Control & Value Area

- **Point of Control (POC)** — The price level with the highest traded volume. Displayed as a configurable line with thickness, color, dash style, and opacity controls. Optional left extension across the chart.
- **Value Area (VAH/VAL)** — Configurable percentage (default 70%). Value Area bars render in a distinct color. Optional VAH/VAL boundary lines with independent styling. Optional left extension.

---

## Reference Levels

### Previous Day Levels
POC, VAH, VAL, High, and Low from the prior trading session. Each level has fully independent color, line style, thickness, and opacity controls.

### Previous Week Levels
POC, VAH, VAL, High, and Low from the prior trading week (Sunday 6 PM – Friday 5 PM). Same independent styling as previous day levels.

### Overnight Session Levels
POC, VAH, VAL, High, and Low for the overnight session. Default window is 6:00 PM – 8:30 AM ET, fully configurable via start/end time settings. Each level independently styled.

---

## Naked Levels

Tracks POC, VAH, and VAL levels from prior sessions and weeks that haven't been revisited by price.

**Session Naked Levels**
- Naked POC, Naked VAH, Naked VAL from prior daily sessions
- Configurable max sessions to display
- Configurable touch count removal — automatically remove levels after N touches (0 = never remove)
- Option to keep filled levels visible after session close

**Weekly Naked Levels**
- Naked POC, Naked VAH, Naked VAL from prior weekly sessions
- Independent max weeks to display and touch count removal settings

**Display Options**
- Touch count shown in level labels (optional)
- Price values in labels (optional)
- Configurable label font size
- All naked level colors, line styles, thickness, and opacity are independently customizable

---

## Dual Profile Mode

Overlays both a Weekly profile and a Session profile side-by-side on the right edge of the chart. Each profile has completely independent settings:

- Independent number of volume bars, bar thickness, volume type, and opacity
- Independent POC and Value Area display with their own colors, line thickness, and opacity
- Independent POC and VA line extension toggles
- Configurable width for each profile and gap between them
- Optional custom daily session times for the session profile
- Session profile style: Filled Bars or Smooth Outline (with configurable outline smoothness)

---

## Low Volume Nodes (LVN)

Detects and highlights low-volume gaps within the profile — areas where price moved quickly and may act as future support/resistance.

- Configurable number of rows (granularity of detection)
- LVN Detection % threshold (lower = more sensitive)
- Show Adjacent LVN Nodes option to create wider zones
- Customizable fill color, fill opacity, border color, and border opacity

---

## Candle Profiles

Tick-based volume profiles rendered on individual candles, extending to the right of each bar.

- Configurable profile width in pixels
- POC highlight on each candle
- Value Area highlight with configurable percentage
- VAH/VAL lines on candle profiles with independent color, thickness, and opacity
- Volume type: Standard, Bullish, Bearish, or Both (with independent bullish/bearish colors)
- Opacity control per candle profile

---

## Move Profiles (Experimental)

Automatically detects breakout moves from consolidation zones and builds a volume profile for each completed move.

- **Consolidation Bars** — Number of bars with no new swing highs/lows to define consolidation
- **Breakout Threshold** — Ticks beyond consolidation range to trigger a breakout
- **Minimum Move Size** — Filters noise by ignoring moves smaller than N ticks
- **Maximum Moves to Display** — Show only the most recent N completed moves
- POC and VA lines on each move profile with independent color, style, and thickness

---

## DOM Visualization (Domdicator)

Live order book depth visualization rendered directly on the chart. Shows bid/ask depth as horizontal bars at each price level with volume text labels.

- Real-time and historical order tracking
- Dynamic threshold calculation for outlier detection
- Configurable width, gap, and right extension
- Volume text labels with min/max font size scaling
- Live vs. historical opacity controls
- Bid/Ask/Text/Outlier colors
- Minimum orders threshold to begin rendering

> **Note:** DOM settings are currently hidden from the GUI and configured via NinjaScript properties.

---

## Rendering & Visual Options

**Volume Display Types:** Standard, Bullish, Bearish, or Both (split delta coloring)

**Gradient Fill** — Optional gradient effect on volume bars that fades from transparent to solid, with configurable intensity (0–100).

**Adaptive Rendering** — Auto-sizes bars to fill available pixel space and smooths the profile shape with Gaussian smoothing passes. Configurable min/max bar pixel height to prevent bars from disappearing when zoomed out or getting too thick when zoomed in.

**Render Quality:** Manual (fixed bar thickness) or Adaptive (auto-sizing with smoothing).

---

## Alerts

Proximity alerts when price approaches any key level:

- **Alert targets:** Previous Day levels, Previous Week levels, Overnight levels, Naked Session levels, Naked Weekly levels — each category can be toggled independently
- **Alert Distance** — Configurable in ticks (1–100)
- **Sound alerts** — Custom .wav file support
- **Auto-rearm on new session** — Reset all alerts at session start

---

## Additional Details

- Every line, level, and label is independently customizable — color, dash style, thickness, opacity
- Touch count tracking with optional label display
- Price value labels on all reference levels
- British/US date format support
- Configurable update frequency for historical bar performance
- Exposed plot outputs for POC, VAH, VAL, PD levels, PW levels, and Overnight levels — usable by strategies or other indicators
- Debug output option for troubleshooting

---

## Installation

1. Download the `.cs` file from this repository
2. Open NinjaTrader 8
3. Go to **Tools → Import → NinjaScript Add-On**
4. Select the downloaded file and click **OK**
5. The indicator will appear in your **Indicators** list — add it to any chart

---

## Part of the RedTail Indicators Suite

This indicator is part of the [RedTail Indicators](https://github.com/3astbeast/RedTailIndicators) collection — free NinjaTrader 8 tools built for futures traders who demand precision.

---

<p align="center">
  <a href="https://buymeacoffee.com/dmwyzlxstj">
    <img src="https://img.shields.io/badge/☕_Buy_Me_a_Coffee-Support_My_Work-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black" alt="Buy Me a Coffee"/>
  </a>
</p>
