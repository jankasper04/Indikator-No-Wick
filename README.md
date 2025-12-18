# iFVG Multi-Timeframe Strategy für TradingView

## 📁 Dateien

| Datei | Beschreibung |
|-------|--------------|
| `iFVG_Strategy_Description.md` | Ausführliche Strategie-Dokumentation |
| `iFVG_Strategy_Indicator.pine` | TradingView Pine Script v5 Indikator |

---

## 🚀 Quick Install

1. Öffne [TradingView](https://www.tradingview.com)
2. Gehe zu **Pine Editor** (unten)
3. Kopiere den Inhalt von `iFVG_Strategy_Indicator.pine`
4. Klicke **Add to Chart**
5. Fertig!

---

## 📋 Strategie-Ablauf

```
┌─────────────────────────────────────────────────────────┐
│  1. LIQUIDITY SWEEP (H1/M15)                           │
│     └── SSL für Long / BSL für Short                   │
├─────────────────────────────────────────────────────────┤
│  2. HTF FAIR VALUE GAP (M5/M15/H1)                     │
│     └── Richtung bestätigt den Bias                    │
├─────────────────────────────────────────────────────────┤
│  3. INVERSION FVG (M1)                                 │
│     └── Entry-Zone identifiziert                       │
├─────────────────────────────────────────────────────────┤
│  4. CISD - Change in State of Delivery (M1)            │
│     └── Finale Bestätigung                             │
├─────────────────────────────────────────────────────────┤
│  5. ENTRY → TARGET (BSL/SSL)                           │
│     └── Nächstes Liquiditätslevel als TP              │
└─────────────────────────────────────────────────────────┘
```

---

## ⚡ Schnellübersicht

### Long Setup ✅
- SSL Sweep erkannt
- Bullisher HTF FVG
- Bullisher iFVG (M1)
- CISD bullish
- **Target**: Nächste BSL

### Short Setup ✅
- BSL Sweep erkannt
- Bearisher HTF FVG
- Bearisher iFVG (M1)
- CISD bearish
- **Target**: Nächste SSL

---

## 🎯 Empfohlene Märkte

- **NQ1!** (Nasdaq Futures)
- **ES1!** (S&P 500 Futures)
- **Forex Majors**
- **Crypto (BTC, ETH)**

---

## ⏰ Beste Trading-Zeiten

| Session | Zeit (UTC) | Volatilität |
|---------|------------|-------------|
| London Open | 07:00-10:00 | ⭐⭐⭐ |
| NY Open | 13:00-16:00 | ⭐⭐⭐ |
| London Close | 15:00-17:00 | ⭐⭐ |

---

*Trade safe! 📈*
