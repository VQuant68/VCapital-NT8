# VCapital NT8 — Automated DCA Grid Trading Strategy

<div align="center">

![NinjaTrader 8](https://img.shields.io/badge/Platform-NinjaTrader%208-blue?style=for-the-badge)
![NQ/ES](https://img.shields.io/badge/Markets-NQ%20%7C%20ES-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)

**Professional automated trading strategy for NQ & ES futures on NinjaTrader 8**

</div>

---

## 📋 Overview

**VCapital** is a battle-tested automated trading strategy built for the **NinjaTrader 8** platform. It combines a **Dollar Cost Averaging (DCA) Grid** system with a **Multi-Factor Trend Detection** engine to trade NQ (Nasdaq 100) and ES (S&P 500) E-mini futures.

### Why VCapital?

- 🎯 **Multi-Factor Trend Detection** — EMA crossover + Donchian breakout + Macro SMA scoring
- 📊 **Smart DCA Grid** — Adaptive position sizing with configurable multiplier
- 🛡️ **Advanced Risk Management** — Drawdown cutoff, P&L auto-stop, price range filters
- ⏰ **21-Period Scheduler** — Pre-configured trading calendar with walk-forward optimization
- 📺 **Real-time Dashboard** — Live P&L, position count, trend status via SharpDX overlay
- 📝 **CSV Trade Logging** — Full audit trail for every trade

---

## 🏗️ Strategy Architecture

```
VCapital Strategy
├── Core Trading Engine
│   ├── DCA Grid System (Managed & Unmanaged orders)
│   ├── Multi-Factor Trend Detection
│   └── Basket TP / DD Cutoff Risk Management
├── Mode System
│   ├── Auto Mode (4-factor scoring)
│   ├── OnlyBuy / OnlySell (Manual direction)
│   └── Time Period Scheduler (21 periods)
├── Risk Controls
│   ├── Drawdown Cutoff + Cooldown
│   ├── Auto ON/OFF by P&L
│   ├── Auto ON/OFF by Price Range
│   └── Session Hour Filter
└── Dashboard & Logging
    ├── Real-time SharpDX Dashboard
    └── CSV Trade Logging
```

## 📊 Multi-Factor Trend Detection

The Auto mode uses a **4-factor scoring system** to determine trend direction:

| Factor | Indicator | Weight | Description |
|--------|-----------|--------|-------------|
| **EMA Crossover** | EMA Fast/Slow | ±2 | Primary trend signal |
| **Donchian Breakout** | Channel High/Low | ±1 | Momentum confirmation |
| **Macro SMA** | Long-period SMA | ±1 | Market regime bias |
| **Smoothing** | N-bar filter | — | Anti-whipsaw protection |

**Score ≥ 3 → BUY** | **Score ≤ -3 → SELL**

---

## ⚙️ Key Parameters

| Category | Parameter | Default | Description |
|----------|-----------|---------|-------------|
| Core | `Initial_Contracts` | 1 | Starting lot size |
| Core | `Lot_Multiplier` | 1.25× | DCA scaling factor |
| Core | `Grid_Distance` | 4000 pts | Grid spacing |
| Core | `Take_Profit` | 500 pts | Basket TP target |
| Risk | `DD_Cutoff` | 90% | Max drawdown limit |
| Risk | `DD_Cooldown` | 2 days | Recovery pause |
| Trend | `EMA_Fast / Slow` | 21 / 55 | EMA periods |
| Trend | `Donchian_Period` | 20 | Channel period |
| Trend | `Macro_SMA` | 50 | Regime filter SMA |

---

## 📦 What's Included

| File | Description |
|------|-------------|
| 📄 `VCapital_User_Guide.pdf` | Comprehensive setup & usage guide |

> **Note:** Source code is distributed separately under a proprietary license. Contact us for access.

## 🚀 Getting Started

1. **Obtain** the strategy file (`.cs`) through authorized channels
2. **Copy** to `Documents\NinjaTrader 8\bin\Custom\Strategies\`
3. **Compile** in NinjaScript Editor (F5)
4. **Configure** parameters in Strategy Analyzer
5. **Backtest** or enable for live trading

Refer to the **User Guide PDF** for detailed setup instructions.

---

## 📞 Contact

For licensing inquiries, custom development, or support:

- **Developer:** VQuant
- **GitHub:** [@VQuant68](https://github.com/VQuant68)

## ⚠️ Disclaimer

This software is provided for educational and research purposes only. Trading futures involves substantial risk of loss and is not suitable for all investors. Past performance is not indicative of future results. Use at your own risk.

---

<div align="center">

*Developed by VQuant — Professional Quantitative Trading Solutions*

</div>
