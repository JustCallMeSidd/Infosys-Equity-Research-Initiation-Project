# Infosys Limited (NSE: INFY) — Equity Research Initiation Package

[![Financial Model: Excel](https://img.shields.io/badge/Financial%20Model-14--Sheet%20Excel-green.svg)](Infosys_Equity_Research_Model.xlsx)
[![Analytics: Python](https://img.shields.io/badge/Analytics-Python%20EDA%20Notebook-blue.svg)](Infosys_EDA.ipynb)
[![Report: Institutional](https://img.shields.io/badge/Research%20Report-14--Page%20Word-navy.svg)](Infosys_Initiation_Report.docx)
[![Target: BUY](https://img.shields.io/badge/Recommendation-BUY%20(₹1,315)-brightgreen.svg)](#the-investment-thesis)

Comprehensive, institutional-grade sell-side equity research initiation package on **Infosys Limited (NSE: INFY | BSE: 500209)** prepared for the **Research Analyst role at J.P. Morgan's Global Research Center, Mumbai (Commercial & Investment Bank)**.

---

## The Investment Thesis in Three Lines
1. **Cyclical Margin Floor Reached (~21% EBIT / 23.7% EBITDA):** Operating margins have absorbed post-COVID normalization; Project Maximus cost takeout and Topaz AI delivery establish a durable floor.
2. **Pristine Cash Conversion & Capital Return (>85% FCF Returned):** Asset-light capex (~1.5% sales) enables >95% FCF conversion (FY26 FCF: ₹31,259 Cr), backed by ₹49,912 Cr in net cash ($6.0B) and a 3.7% dividend yield.
3. **Severe Valuation Disconnect (Trading Below -1σ Band at 14.3x P/E):** Unwarranted 48% discount to TCS (27.5x) despite matching 31.7% ROE and superior FY26 revenue growth (+9.6% vs TCS 5.5%), offering an asymmetric risk-reward with **+26.7% upside to our ₹1,315 DCF target price**.

---

## Deliverables & Repository Structure

```text
Infosys Equity Research Initiation Project/
├── Infosys_Equity_Research_Model.xlsx    # Full 14-sheet integrated financial model (openpyxl)
├── Infosys_Initiation_Report.docx        # 14-page institutional sell-side initiation report
├── Infosys_1Page_Note.docx               # Executive 1-page tear sheet (Word format)
├── Infosys_EDA.ipynb                     # 16-section reproducible Python EDA & analytics notebook
├── README.md                             # Project overview, workflow guide & documentation
├── Resume_Bullets.md                     # Tailored CV bullets & project descriptions
├── Interview_Prep.md                     # 60-second pitch and 30 institutional model Q&As
├── requirements.txt                      # Python dependencies for headless replication
├── generate_eda_and_charts.py            # Automated chart and notebook pipeline script
├── build_full_model_14sheets.py          # Complete 14-sheet Excel model generator
├── build_one_page_note.py                # Institutional 1-page note generator script
├── build_initiation_report.py            # Institutional report generator script
├── charts/                               # 12 publication-grade figures at 300 DPI
│   ├── chart_01_growth_trends.png
│   ├── chart_02_margin_analysis.png
│   ├── chart_03_dupont_analysis.png
│   ├── chart_04_cash_flow_quality.png
│   ├── chart_05_working_capital.png
│   ├── chart_06_capital_allocation.png
│   ├── chart_07_quarterly_trends.png
│   ├── chart_08_valuation_pe_bands.png
│   ├── chart_09_peer_benchmarking.png
│   ├── chart_10_correlation_matrix.png
│   ├── chart_11_forecast_backtest.png
│   └── chart_12_monte_carlo_dcf.png
└── data/                                 # Audited source data & CSV outputs
    ├── Infosys_Financial_Model_.xlsx     # Raw Screener master export
    ├── historical_financials.csv         # 10-year consolidated dataset
    ├── peer_benchmarks.csv               # Indian IT peers comparison table
    └── monte_carlo_results.csv           # 10,000-run simulation outputs
```

---

## Excel Financial Model Architecture (`Infosys_Equity_Research_Model.xlsx`)

The workbook follows global investment banking financial modeling conventions:
- **Font Styling:** Blue (`#002060`) for hardcoded inputs; Black (`#000000`) for in-sheet formulas; Green (`#008000`) for cross-sheet references; Yellow fill (`#FFF2CC`) for key scenario assumptions; Green fill (`#E2EFDA`) for audit sign-offs.
- **Formulas:** Clean standard Excel syntax (`INDEX`, `MATCH`, `CHOOSE`, `IF`, `SUM`, `AVERAGE`), guarded against divide-by-zero. Zero circular references.

### 14 Core Worksheets (Exact Sequence):
1. **Cover:** Executive overview, recommendation card, formatting legend, and disclaimer.
2. **Summary:** Financial summary dashboard (FY24A–FY31E), KPI matrix, and valuation synthesis.
3. **Assumptions:** Macro, operational, and capital structure drivers across Bear, Base, and Bull cases with active scenario selector (`CHOOSE`).
4. **Source Data:** Unaltered copy of Screener master dataset (audited single source of truth).
5. **Historical:** FY17–FY26 Income Statement, Balance Sheet, and Cash Flow Statement, all formula-linked to Source Data with reconciliation checks.
6. **Ratios:** 10-year growth rates, margins, 3-stage DuPont ROE decomposition, working capital days (DSO, DPO, CCC), cash quality, and valuation multiples.
7. **Forecast:** Driver-based integrated 3-statement forecast (FY27E–FY31E) with dynamic cash plug linked to the Cash Flow Statement.
8. **WACC:** Capital Asset Pricing Model (CAPM) build (Rf 7.05%, Beta 0.85, ERP 5.50% = 11.725% WACC).
9. **DCF:** Unlevered Free Cash Flow (FCFF) valuation, mid-year convention, Gordon Growth terminal value, and net cash equity bridge.
10. **Sensitivity:** Dynamic 2D matrices: WACC vs Terminal Growth, and Revenue CAGR vs EBITDA Margin.
11. **Comps:** Peer valuation benchmarking across TCS, HCLTech, Wipro, Tech Mahindra, and LTIMindtree.
12. **Scenarios:** Probability-weighted valuation (Bear 20% @ ₹1,120, Base 60% @ ₹1,315, Bull 20% @ ₹1,540).
13. **Football Field:** Comparative valuation range bridge across all methodologies.
14. **Checks:** Master automated integrity audit dashboard (10 validation checks showing PASS).

---

## How to Run & Reproduce

### 1. Environment Setup
```bash
pip install -r requirements.txt
```

### 2. Run Python Analytics & Rebuild Charts
```bash
python generate_eda_and_charts.py
```

### 3. Rebuild the 14-Sheet Excel Financial Model
```bash
python build_full_model_14sheets.py
```

### 4. Rebuild the Research Report and One-Page Tear Sheet
```bash
python build_one_page_note.py
python build_initiation_report.py
```

### 5. Execute the Jupyter Notebook
```bash
jupyter nbconvert --execute --inplace Infosys_EDA.ipynb
```

---

## Model Reconciliations & Quality Bar Check

| Audit Check | Target Condition | Verification Result | Sign-Off |
|---|---|---|---|
| **CHK-01: Balance Sheet Integrity** | Assets = Liabilities (FY17–FY26) | Exact 0.0 variance across all 10 years | **PASS (OK)** |
| **CHK-02: Forecast Balance Sheet** | Assets = Liabilities (FY27E–FY31E) | Exact 0.0 variance across all 5 years | **PASS (OK)** |
| **CHK-03: Cash Flow Reconciliation** | BS Cash = CF Closing Cash | Perfectly tied via dynamic cash plug | **PASS (OK)** |
| **CHK-04: Operating Identity** | Sales - Expenses = EBITDA | Exact zero variance | **PASS (OK)** |
| **CHK-05: PBT Identity** | EBIT + OthInc - Int = PBT | Exact zero variance | **PASS (OK)** |
| **CHK-06: Terminal Growth Safety** | g < WACC by at least 3.0% | g (4.5%) is 722 bps below WACC (11.7%) | **PASS (OK)** |
| **CHK-07: Scenario Probability** | Sum of Weights = 100% | 20% + 60% + 20% = 100.0% | **PASS (OK)** |
| **CHK-08: Cash Solvency** | Minimum Forecast Cash > 0 | Maintained > ₹35,000 Cr in all years | **PASS (OK)** |
| **CHK-09: Formula Errors** | Zero #REF!, #DIV/0!, #NAME? | Zero formula errors across workbook | **PASS (OK)** |
| **CHK-10: Consistency Mapping** | Report matches Excel model | 100% parameter match in Table 4 | **PASS (OK)** |

---

## Items to Refresh Before Live Interview Submission

The following market parameters fluctuate daily and should be checked on submission day:
1. **Infosys Current Share Price (CMP):** Update CMP from NSE closing feed (currently pegged at ₹1,037.70).
2. **10-Year India Sovereign G-Sec Yield:** Update benchmark Rf (currently 7.05%, RBI).
3. **Infosys 5-Year Beta:** Refresh beta vs Nifty 50 (currently 0.85).
4. **Peer Trading Multiples:** Refresh market cap, P/E, and EV/EBITDA for TCS, HCLTech, Wipro, TechM, and LTIM.
5. **Latest Management Guidance:** Update constant currency revenue growth guidance from latest quarterly earnings call (currently 4.0%–7.0%).

---

## Known Limitations

1. **Condensed Balance Sheet:** Other Assets and Other Liabilities are consolidated in the source Screener dataset, requiring percentage-of-sales driver modeling.
2. **Lease Liability Classification:** FY26 reported borrowings (₹9,176 Cr) represent Ind AS 116 lease liabilities rather than funded financial debt. Infosys operates with zero bank borrowings.
3. **Segmental Margins:** Segment-level operating profit (BFSI vs Manufacturing vs Retail) is not reported quarterly in condensed feeds, necessitating corporate-level margin forecasting.

---

## Legal & Educational Disclaimer

*This is an independent educational research project prepared by a student candidate using publicly available information. It is not investment advice and is not affiliated with or endorsed by any financial institution.*
