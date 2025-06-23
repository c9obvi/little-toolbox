# 🧠 Bitcoin Mining Cheat Sheet: Terms & Metrics

> This guide explains key terms, formulas, and comparisons used in Bitcoin mining, written for miners, resellers, and prosumers.

---

## 🧾 Core Terminology

| 📌 **Term**              | 🧠 **Definition**                                                                 |
|--------------------------|----------------------------------------------------------------------------------|
| ⚡ **Hashrate (TH/s)**   | Trillions of hashes computed per second. Higher = more mining power.             |
| ⚙️ **Joules per Terahash (J/TH)** | Energy needed to process 1 TH/s. Lower is better (more efficient).             |
| 🔋 **Watt (W)**          | Unit of power. 1 W = 1 joule per second. 7,000 W = 7,000 J/s consumed.           |
| 🔢 **Efficiency**        | Often written as **J/TH**. Multiply by TH/s to get total watts: `J/TH × TH/s = W`. |
| 💰 **Hashprice ($/TH/day)** | Revenue earned per terahash per day. e.g. `$0.0546/TH/day`.                        |
| 📉 **Cost per TH ($/T)** | What a seller charges per terahash. Used to price mining hardware.             |
| ⛏️ **ASIC**              | Application-Specific Integrated Circuit — purpose-built for mining.             |
| 💧 **Immersion Cooling** | Miner submerged in dielectric fluid for max heat dissipation.                  |
| 🚿 **Hydro Cooling**     | Water-cooled miner using cold plates and a liquid loop.                        |

---

## 📐 Quick Formulas

#### 🔄 Convert J/TH to Power
```txt
Power (W) = J/TH × TH/s
```

#### ⚡ Convert Power to Daily Energy Use
```txt
kWh/day = (Watts ÷ 1000) × 24
```

#### 💵 Estimate Daily Profit
```txt
Net Profit = (Hashprice × TH/s) – (kWh/day × $/kWh)
```

---

## 📊 Example Breakdown

| Miner            | Hashrate | J/TH | Power (W) | kWh/day | Cost/day (@$0.10/kWh) | Net Profit (est.) |
|------------------|----------|------|-----------|---------|------------------------|--------------------|
| Antminer S21 Pro | 234 TH/s | 15   | 3,510     | 84.2    | $8.42                  | ~$4.35             |
| S21 XP Hydro     | 473 TH/s | 12   | 5,676     | 136.2   | $13.62                 | ~$12.23            |

---

## 💡 Buyer Tip: $/TH vs. ROI

When evaluating a miner:
- Multiply `$ per TH` × TH/s = full machine cost
- Divide that by net earnings/day = **breakeven time**

---

## ✅ Recommended Ratios to Watch

| 🔍 **Metric**         | 🧠 **What to Look For**                                                   |
|-----------------------|---------------------------------------------------------------------------|
| J/TH                  | Lower is better. <14 = excellent.                                         |
| $/TH                  | Lower is cheaper. Used units often range $1.50–$5. New immersion units: $12–$20. |
| Power Efficiency (W)  | Lower total W = easier cooling and reduced power bills.                   |
| Hashprice             | Dynamic with BTC price, block reward, and network difficulty.             |
| Daily ROI             | Should justify total machine cost in 9–18 months (depending on scale & cooling). |

---

## 🧩 Can I use this in Notion?

✅ Yes!  
- Paste this Markdown directly into Notion — it auto-converts it.
- You can then clean it up, add toggles, and embed your calculator sheets.

---

## 🔗 Clone This Template

Want to turn this into a live GitHub Page?

1. Create a repo (e.g., `mining-cheatsheet`)
2. Drop this into `README.md`
3. Enable Pages under **Settings → Pages → main branch**
4. Optional: Add GitHub badge links, price APIs, or ROI calculators