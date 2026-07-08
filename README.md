# 📈 Momentum Investing on PSX — Final Year Project

![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Finance](https://img.shields.io/badge/Quantitative_Finance-0057B7?style=for-the-badge&logo=refinitiv&logoColor=white)
![Research](https://img.shields.io/badge/Academic_Research-8B0000?style=for-the-badge&logo=googlescholar&logoColor=white)

> **"A Case Study of Momentum Investing on Selected PSX Stocks: Evaluating Rebalancing Frequency for Pakistani Retail Investors"**
>
> Final Year Project — BS Actuarial Science & Risk Management, Institute of Business Management (IoBM), Karachi
>
> 👥 Group Project — Abdul Rasheed · Daniyal Sabir · Abdul Nafay
> 👨‍🏫 Supervisor: Sir Sohail Ahmed Khan

---

## 📌 Project Overview

Momentum investing — buying recent winners and avoiding recent losers — is well-documented in developed markets. But for **Pakistani retail investors**, a critical practical question is largely unanswered: **how often should you actually rebalance?**

This project answers that question directly. Using **10 years of monthly price data (Jan 2015 – Dec 2024)** for 8 liquid PSX-listed stocks, we tested 9 combinations of portfolio size and rebalancing frequency — with realistic PSX transaction costs and Pakistan's capital gains tax (CGT) structure applied at every rebalance.

---

## 🏦 Stocks Analysed

| Ticker | Company |
|---|---|
| OGDC | Oil & Gas Development Company |
| MEBL | Meezan Bank |
| EFERT | Engro Fertilizers |
| MCB | MCB Bank |
| LUCK | Lucky Cement |
| FFC | Fauji Fertilizer Company |
| SAZEW | Sazgar Engineering |
| MARI | Mari Petroleum |

**Benchmark:** KSE-100 Index · **Risk-Free Rate:** 3-Month T-Bill (Pakistan) · **Period:** Jan 2015 – Dec 2024 (120 months)

---

## 🔬 Methodology

### Momentum Signal
- **Formation period:** 6 months trailing return
- Stocks ranked by trailing 6-month cumulative return at each rebalancing point
- **Top N** stocks selected into equal-weighted portfolio

### Scenarios Tested (9 total)

| Portfolio Size | Rebalancing Frequency |
|---|---|
| Top 2 stocks | Annual |
| Top 3 stocks | Semi-Annual |
| Top 5 stocks | Quarterly |

### Realistic Cost Modelling
- **Transaction costs:** 0.35% one-way (brokerage + CDC charges) applied on both buy and sell
- **Capital Gains Tax (CGT):**
  - < 1 year holding: **15%**
  - 1–2 years holding: **12.5%**
  - > 2 years holding: **0%**
- Full portfolio turnover assumed at every rebalance (conservative approach)
- CGT applied on realised gains at portfolio level at every rebalancing point

### Performance Metrics
- Annualised Return
- Annualised Volatility
- **Sharpe Ratio** (primary metric)
- Maximum Drawdown
- CAPM Alpha & Beta

---

## 📊 Key Results

### Risk-Adjusted Performance by Scenario

| Portfolio | Frequency | Sharpe Ratio | Max Drawdown | vs KSE-100 |
|---|---|---|---|---|
| Top 2 | Annual | **0.571** | -53.9% | ✅ Outperforms |
| **Top 3** | **Annual** | **0.555** ⭐ | **-42.3%** | ✅ Outperforms |
| Top 5 | Annual | 0.489 | -38.1% | ✅ Outperforms |
| Top 2 | Semi-Annual | 0.412 | -55.2% | ✅ Outperforms |
| Top 3 | Semi-Annual | 0.398 | -44.7% | ✅ Outperforms |
| Top 5 | Semi-Annual | 0.367 | -39.8% | ✅ Outperforms |
| Top 2 | Quarterly | 0.301 | -57.4% | ✅ Outperforms |
| Top 3 | Quarterly | 0.289 | -46.1% | ✅ Outperforms |
| Top 5 | Quarterly | 0.251 | -41.2% | ✅ Outperforms |
| KSE-100 | — | 0.198 | -47.3% | Benchmark |

---

## 💡 Key Findings

**1. Annual rebalancing dominates across every portfolio size**
Every annual scenario beats its semi-annual and quarterly equivalents. More frequent rebalancing generates more CGT events and higher cumulative transaction costs — costs that consistently outweigh the benefit of fresher momentum signals.

**2. All 9 scenarios beat the KSE-100 on a risk-adjusted basis**
Every combination of portfolio size and rebalancing frequency outperformed the benchmark's Sharpe ratio of 0.198 — confirming momentum as a viable strategy for PSX retail investors even after realistic frictions.

**3. Top 3 Annual is the optimal practical recommendation**
Although Top 2 Annual has a marginally higher Sharpe ratio (0.571 vs 0.555), its maximum drawdown of -53.9% is significantly deeper than Top 3 Annual's -42.3%. For a retail investor who cannot ride out a near-54% peak-to-trough loss, Top 3 Annual offers the best balance of risk-adjusted return and downside protection.

**4. Pakistan's CGT structure materially rewards patience**
The step-down CGT brackets (15% → 12.5% → 0%) directly penalise frequent trading. This structural feature of Pakistan's tax regime is a key mechanism driving the annual rebalancing advantage — a finding specific to the PSX context.

---

## 🛠️ Tools & Techniques

- **Microsoft Excel** — full formula-driven workbook (no programming/statistical software)
- Monthly return computation from raw price data
- Sharpe ratio, maximum drawdown, CAPM alpha/beta calculations
- Scenario analysis across 9 portfolio-frequency combinations
- Data cleaning: date encoding correction, text-to-numeric conversion, bi-weekly to monthly T-Bill conversion
- Dynamic assumptions sheet as single source of truth (all scenarios reference it by formula)

---

## 📁 File Structure

```
📁 psx-momentum-investing-fyp/
├── FYP_Workbook.xlsx          # Full Excel model — all 9 scenarios, raw data, assumptions
├── FYP_Report_Final.docx      # Complete academic report (methodology, results, conclusions)
├── README.md
```

### Workbook Sheets
| Sheet | Contents |
|---|---|
| README | Workbook guide and data cleaning notes |
| Assumptions | All model parameters (single source of truth) |
| Raw_Prices | Monthly closing prices for 8 PSX stocks (2015–2024) |
| KSE100_Benchmark | Monthly KSE-100 index levels |
| RiskFree | Monthly 3-Month T-Bill yield (converted from bi-weekly auctions) |
| Returns | Monthly simple returns for all 8 stocks + KSE-100 |

---

## 🎓 Academic Context

- **Degree:** BS Actuarial Science & Risk Management, IoBM Karachi
- **Motivated by:** Foltice & Langer (2015) — momentum for individual investors with realistic frictions
- **Builds on:** Jegadeesh & Titman (1993), Carhart (1997) four-factor model
- **Pakistan-specific contribution:** First to model PSX momentum with CGT step-down brackets and CDC charges explicitly applied

---

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/abdul-rasheed-551814244)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:sheikhabdulrasheed2003@gmail.com)
