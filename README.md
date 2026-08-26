# 💳 Platinum 365 — From Card to Companion

**Amex Premium Card Growth Strategy** | American Express Campus Challenge 2026 · Strategy Track — Round 2
- **Team:** Thinkers
- **Members:** Vansh Bhandari, Muskan, Shlok Suraiya
- **Institute:** IIT Guwahati
- 🏅 **Top 20 nationally in Round 1**

---

## 🚀 Overview

The Amex Premier Card is built for the 4 days a year members travel, not the 361 they live. We identified a **₹89,300/yr perceived value deficit per card** across a 40K-cardholder portfolio at high attrition risk — then built a cost-constrained **Flex Engine** that reallocates benefits to what each member will actually use.

**Core insight:** the fix isn't *more* benefits, it's more *relevant* benefits.

**Outcome:** ₹132 Cr 5-year NPV of retained revenue · churn down 10% relative · 8% spend uplift.

This submission advanced from Round 1, where the team placed in the **national Top 20**.

---

## 🔍 The Problem

| Finding | Signal |
|---|---|
| Did not use Golf / Airport Transfers / Travel Insurance | 68% / 48% / 48% |
| "Benefit didn't fit my lifestyle" | 41.7% → **Relevance Gap** |
| "Forgot it existed" / too much effort | 29.2% → **Visibility Gap** |
| Felt they got ≤ annual-fee value | 39.1% |

Benefit utilisation sits at ~24%, and the gap is widening 3–4% YoY. Across the portfolio that's **₹230 Cr of unfelt value** — headroom competitors are actively pricing against.

---

## 🧠 Core Features

### Research & Diagnosis
- 📋 Primary survey of premium cardholders → utilisation gaps and root causes
- 💬 1,000+ Amex India app reviews scraped → 4.3★ overall, but 36% negative on deep usage
- 📊 RBI market data (Jun'25 → Jun'26): India card base +9.6%, Amex −7.5%, Amex spend/card +25.6%

### Flex Engine — cost-constrained benefit allocation
- 🎲 **Synthetic portfolio:** 40,000 cardholders + ~3M transactions, calibrated to Amex India FY25 financials
- 🧠 **Propensity model:** LightGBM, out-of-fold **0.91 AUC**, StratifiedGroupKFold (leak-proof)
- 🎒 **Knapsack Optimizer:** maximise Σ(propensity × value) subject to a hard **≤ ₹20,000/card** ceiling
- 💸 Committed cost ₹13,849/card, leaving ₹6,151 headroom that funds personalised nudges
- 📈 Modelled utilisation lift for the Underused archetype: **18% → 64%**

### Benefit Exchange — budget-neutral by design
Members swap a low-relevance perk for a high-relevance one:
```
Relevance      R = P(member uses benefit)
Customer value CV = BenefitValue × R
Cost guardrail Expected_cost_new ≤ Expected_cost_old
```
Same economics for Amex, higher realised value for the member. If nothing fits, no exchange.

### Personalised Nudges & Product Design
- 🧾 **Value Ledger** — live ₹ counter of value used vs. paid, warns 90 days before renewal
- 🪜 **Milestone Ladder** — replaces the ₹20L cliff with rungs at ₹5L / ₹10L / ₹15L / ₹20L
- 🎛️ **Choice Modules** — Mobility, Culinary, Luxury Retail, Preventive Health, Culture, Household
- 📱 8-screen app flow repositioning the app from a bill portal to a Value & Retention Engine

> Classical ML computes the recommendation; the LLM only writes the member-facing copy.

---

## 🛠️ Tech Stack

- **AI/ML:** LightGBM, scikit-learn, greedy knapsack optimisation
- **Data:** Pandas, NumPy, Parquet
- **Viz / Dashboard:** Matplotlib, Plotly, Streamlit
- **Scraping & NLP:** Selenium, review sentiment + theme tagging
- **Modelling:** Excel financial model (NPV, scenarios, sensitivity)
- **Design:** Figma (8-screen prototype)

---

## 💰 Value Economics

| Metric | Value |
|---|---|
| Perceived value deficit addressed | **₹89,300 / card / yr** |
| Benefit cost per card | ₹13,849 (vs ₹20,000 ceiling) |
| Face value delivered | ₹53,200 → **3.48× leverage** |
| Contribution per card/yr | ₹22,129 → ₹28,064 (**+₹5,935**) |
| Self-funded share | ~85% |
| **5-year NPV** | **₹132 Cr** @ 8.3% WACC, payback Year 1 |
| Scenario range | ₹126 Cr (downside) – ₹137 Cr (upside) |

**Sensitivity:** attrition ±3pp → ₹21 Cr · discount rate ±2pp → ₹14.5 Cr · spend uplift ±7pp → ₹9.5 Cr.

> At ₹60,000 with no redesign, the same model returns NPV **−₹22 Cr**. The benefits earn the price — the price doesn't earn itself.

---

## 🎯 Impact

### 👤 For Members
- Value they can see, in rupees, before renewal — not after
- Benefits matched to how they actually spend
- Milestone wins 3× a year instead of one all-or-nothing cliff

### 🏦 For Amex
- **Churn 10% → 9%** (10% relative reduction; each 1pp ≈ ₹3 Cr NPV)
- **+8% spend uplift**, card base 40K → 65K by Year 5
- 92.8% fee acceptance at ₹68,000

### 🤝 For Merchants
- Module activation = self-selected intent, so co-funding buys a qualified lead pipeline (30–40% cost shared), not a generic card deal

---

*All figures are modelled on synthetic data calibrated to public sources. No real cardholder data is used. Student submission — not affiliated with or endorsed by American Express.*
