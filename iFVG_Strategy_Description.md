# iFVG Multi-Timeframe Strategy Indicator

## 📊 Strategie Übersicht

Der **iFVG (Inversion Fair Value Gap) Multi-Timeframe Strategy Indicator** ist ein fortschrittliches Trading-Tool, das auf den Konzepten der Smart Money Concepts (SMC) und Inner Circle Trader (ICT) Methodik basiert. Dieser Indikator identifiziert hochwahrscheinliche Einstiegspunkte durch die Kombination mehrerer Zeitrahmen-Analysen.

---

## 🎯 Strategie-Komponenten

### 1️⃣ Liquidity Sweep (H1 / M15)
Der Indikator erkennt automatisch **Liquiditäts-Sweeps** auf den höheren Zeitrahmen:
- **H1 (1-Stunden-Chart)**: Identifiziert größere institutionelle Stops
- **M15 (15-Minuten-Chart)**: Erkennt kurzfristigere Liquiditätspools

**Was wird erkannt:**
- Equal Highs / Equal Lows (EQH/EQL)
- Swing High / Swing Low Durchbrüche
- Stop-Loss-Cluster-Zonen
- Buy-Side Liquidity (BSL) / Sell-Side Liquidity (SSL)

---

### 2️⃣ Higher Timeframe Fair Value Gap (M5 / M15 / H1)
Nach dem Liquidity Sweep sucht der Indikator nach **Fair Value Gaps** auf den höheren Zeitrahmen:

**Fair Value Gap Definition:**
- Drei aufeinanderfolgende Kerzen
- Lücke zwischen Kerze 1 (High/Low) und Kerze 3 (Low/High)
- Zeigt institutionelles Ungleichgewicht an

**Timeframe-Hierarchie:**
| Timeframe | Signifikanz | Typische Größe |
|-----------|-------------|----------------|
| H1        | ⭐⭐⭐ Hoch   | 15-50+ Punkte  |
| M15       | ⭐⭐ Mittel   | 8-25 Punkte    |
| M5        | ⭐ Standard  | 3-15 Punkte    |

---

### 3️⃣ Inversion Fair Value Gap (M1)
Das Herzstück der Strategie - der **iFVG auf M1**:

**Definition:**
Ein Inversion Fair Value Gap entsteht, wenn:
1. Ein ursprünglicher FVG gebildet wird
2. Der Preis durch den FVG hindurchgeht
3. Der FVG als neue Support/Resistance-Zone fungiert (Inversion)

**Bullish iFVG:**
- Ursprünglich bearisher FVG
- Preis schließt über dem FVG
- FVG wird zur Unterstützungszone

**Bearish iFVG:**
- Ursprünglich bullisher FVG
- Preis schließt unter dem FVG
- FVG wird zur Widerstandszone

---

### 4️⃣ Change in State of Delivery (CISD)
Der Indikator bestätigt Entries durch **CISD**:

**CISD Bullish:**
- Preis war im Distribution-Modus (abwärts)
- Wechselt zu Accumulation/Aufwärts-Delivery
- Bestätigt durch Kerzenstruktur auf M1

**CISD Bearish:**
- Preis war im Accumulation-Modus (aufwärts)
- Wechselt zu Distribution/Abwärts-Delivery
- Bestätigt durch Kerzenstruktur auf M1

---

### 5️⃣ Entry zum nächsten Liquiditäts-Level

**Target-Identifikation:**
- **Buy-Side Liquidity (BSL)**: Swing Highs, Equal Highs
- **Sell-Side Liquidity (SSL)**: Swing Lows, Equal Lows

---

## 📋 Trading-Ablauf (Checkliste)

### 🟢 LONG Setup
```
☐ 1. Liquidity Sweep (SSL) auf H1 oder M15 erkannt
☐ 2. Bullisher HTF-FVG auf M5/M15/H1 identifiziert
☐ 3. Bullisher iFVG auf M1 gebildet (NQ1!)
☐ 4. CISD bullish bestätigt
☐ 5. Entry bei iFVG-Retest
☐ 6. Target: Nächste Buy-Side Liquidity (BSL)
☐ 7. Stop-Loss: Unter dem iFVG Low
```

### 🔴 SHORT Setup
```
☐ 1. Liquidity Sweep (BSL) auf H1 oder M15 erkannt
☐ 2. Bearisher HTF-FVG auf M5/M15/H1 identifiziert
☐ 3. Bearisher iFVG auf M1 gebildet (NQ1!)
☐ 4. CISD bearish bestätigt
☐ 5. Entry bei iFVG-Retest
☐ 6. Target: Nächste Sell-Side Liquidity (SSL)
☐ 7. Stop-Loss: Über dem iFVG High
```

---

## ⚙️ Indikator-Einstellungen

### Timeframe Settings
| Parameter | Standardwert | Beschreibung |
|-----------|--------------|--------------|
| Liquidity TF | H1 | Zeitrahmen für Liquidity Sweep Detection |
| HTF FVG TF | M15 | Zeitrahmen für Higher TF Fair Value Gap |
| Entry TF | M1 | Zeitrahmen für iFVG und CISD |

### Detection Settings
| Parameter | Standardwert | Beschreibung |
|-----------|--------------|--------------|
| Swing Length | 5 | Kerzen für Swing High/Low Erkennung |
| Min FVG Size | 5 Punkte | Minimale Gap-Größe für Erkennung |
| iFVG Lookback | 50 | Kerzen-Lookback für iFVG Suche |
| Show HTF Zones | True | HTF FVG Zonen anzeigen |

### Visual Settings
| Parameter | Standardwert | Beschreibung |
|-----------|--------------|--------------|
| Bullish iFVG Color | 🟢 Grün | Farbe für bullishe iFVG Zonen |
| Bearish iFVG Color | 🔴 Rot | Farbe für bearishe iFVG Zonen |
| Liquidity Color | 🟡 Gelb | Farbe für Liquiditätszonen |
| Show Labels | True | Beschriftungen anzeigen |

---

## 📈 Signaltypen

### Visuell auf dem Chart
- **Rechtecke**: FVG und iFVG Zonen
- **Horizontale Linien**: Liquiditätslevel (BSL/SSL)
- **Pfeile**: Entry-Signale
- **Labels**: Sweep-Ereignisse und CISD

### Alert-Konditionnen
1. `Liquidity Sweep Detected` - H1/M15 Sweep erkannt
2. `HTF FVG Formed` - Neuer HTF Fair Value Gap
3. `iFVG Signal` - Inversion FVG Entry-Signal
4. `CISD Confirmed` - Change in State of Delivery bestätigt
5. `Full Setup Alert` - Komplettes Setup (alle Kriterien erfüllt)

---

## 🎓 Anwendungsbeispiel (NQ1! / Nasdaq Futures)

### Beispiel Long-Trade:
1. **07:30 UTC** - SSL Sweep auf H1 erkannt (Preis nimmt vorheriges Swing Low)
2. **07:45 UTC** - Bullisher FVG auf M15 gebildet (15 Punkte Gap)
3. **08:15 UTC** - iFVG auf M1 identifiziert (ursprünglich bearisher FVG invertiert)
4. **08:16 UTC** - CISD bullish (starke bullishe Kerze)
5. **Entry**: Bei Rücksetzer zum iFVG (~18,450)
6. **Stop-Loss**: 5 Punkte unter iFVG Low (~18,445)
7. **Take-Profit**: Nächste BSL (~18,520)
8. **RRR**: 1:3+

---

## ⚠️ Wichtige Hinweise

### Best Practices:
- ✅ Immer von HTF zu LTF analysieren (Top-Down)
- ✅ Auf Killzones achten (London Open, NY Open)
- ✅ News-Events berücksichtigen
- ✅ Mindest-RRR von 1:2 einhalten

### Vermeiden:
- ❌ Trades ohne HTF Kontext
- ❌ Entries gegen den übergeordneten Trend
- ❌ Übertrading in choppy Markets
- ❌ Trades während High-Impact News

---

## 📊 Performance-Metriken (Backtesting)

Der Indikator bietet integrierte Backtesting-Statistiken:
- Win Rate
- Durchschnittliches RRR
- Profit Factor
- Max Drawdown
- Beste/Schlechteste Trade-Session

---

## 🔧 Kompatibilität

- **Instrumente**: Futures (NQ, ES, YM, RTY), Forex, Crypto, Aktien
- **Empfohlene TF**: M1 für Entry, M5/M15/H1 für Analyse
- **Chart-Typ**: Candlestick (empfohlen)

---

## 📝 Version History

| Version | Datum | Änderungen |
|---------|-------|------------|
| 1.0.0 | 2024-01 | Initial Release |
| 1.1.0 | 2024-02 | CISD Detection hinzugefügt |
| 1.2.0 | 2024-03 | Multi-TF Support erweitert |

---

## 💡 Support & Community

Bei Fragen zur Strategie oder zum Indikator:
- TradingView Kommentare
- Discord Community
- Tutorial Videos

---

*Disclaimer: Dieser Indikator ist ein Analyse-Tool und keine Finanzberatung. Trading birgt Risiken. Vergangene Ergebnisse garantieren keine zukünftigen Gewinne.*
