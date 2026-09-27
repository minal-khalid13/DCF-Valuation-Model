# Nike DCF Valuation Model

A professional-grade Discounted Cash Flow (DCF) valuation model for Nike, Inc. (NKE) built in Excel with comprehensive assumptions, dual terminal value methodologies, and sensitivity analysis.

![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)
![Finance](https://img.shields.io/badge/Finance-DCF%20Model-blue)
![Status](https://img.shields.io/badge/Status-Complete-success)

## 📊 Executive Summary

**Valuation Date:** September 27, 2026  
**Company:** Nike, Inc. (NKE)  
**Current Market Price:** $35.75  

### Valuation Results

| Method | Implied Share Price | Upside/(Downside) |
|--------|--------------------:|------------------:|
| **Gordon Growth Model** | **$42.35** | **+18.5%** |
| **Exit Multiple Method** | **$59.91** | **+67.6%** |

**Key Metrics:**
- WACC: 9.16%
- Terminal Growth Rate: 2.5%
- Exit EV/EBITDA Multiple: 15.0x
- 5-Year Revenue CAGR: 4.2%
- Target EBIT Margin: 12.0% (FY2031E)

---

## 🎯 Project Overview

This repository contains a complete DCF valuation model for Nike built according to professional financial modeling standards. The model:

- ✅ Uses actual Nike financials from FY2022–FY2026
- ✅ Projects 5-year unlevered free cash flows (FY2027E–FY2031E)
- ✅ Calculates WACC using market data (CAPM for equity, debt from financials)
- ✅ Employs two terminal value methods (Gordon Growth & Exit Multiple)
- ✅ Includes comprehensive sensitivity analysis
- ✅ Features professional formatting with color-coded inputs
- ✅ Fully formula-driven with no hardcoded outputs

---

## 📁 Repository Contents

```
DCF-Valuation-Model/
├── Nike_DCF_Model.xlsx          # Main Excel valuation model
├── README_DCF_Model.md          # Comprehensive user guide & methodology
├── dataset/
│   └── Nike.xlsx                # Historical financial data (FY2022-FY2026)
├── prd.md                       # Product Requirements Document
└── README.md                    # This file
```

---

## 🚀 Quick Start

### Prerequisites
- Microsoft Excel 2016 or later (required for formula compatibility)
- Basic understanding of DCF valuation methodology

### Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/minal-khalid13/DCF-Valuation-Model.git
   cd DCF-Valuation-Model
   ```

2. **Open the model**
   - Open `Nike_DCF_Model.xlsx` in Microsoft Excel
   - Navigate to **Tab 2: DCF Model** for valuation results
   - Review **Tab 1: Assumptions** for all inputs and WACC build

3. **Adjust assumptions** (optional)
   - Edit any **blue text** cells with **yellow fill** in the Assumptions tab
   - All calculations update automatically
   - Use sensitivity tables to explore valuation ranges

4. **Read the documentation**
   - See `README_DCF_Model.md` for complete methodology and interpretation
   - Includes detailed explanations of all assumptions and formulas

---

## 📈 Model Structure

### Tab 1: Assumptions

Complete WACC calculation and forecast assumptions:

**Market Inputs**
- Current share price, beta, risk-free rate, equity risk premium
- Diluted shares outstanding, total debt

**Cost of Capital**
- Cost of Equity (CAPM): Rf + β × ERP = **10.73%**
- After-Tax Cost of Debt: **1.65%**
- WACC: **9.16%** (weighted average based on market cap)

**Forecast Assumptions (FY2027E–FY2031E)**
- Revenue growth rates (3% → 5% → 4%)
- EBIT margins (10.0% → 12.0% recovery)
- D&A, CapEx, NWC as % of revenue
- Tax rate (20.31% effective)

**Terminal Value Assumptions**
- Terminal growth rate: 2.5%
- Exit EV/EBITDA multiple: 15.0x

### Tab 2: DCF Model

Complete valuation from historical data through implied share price:

**Historical Financials (FY2022–FY2026)**
- Income statement, margins, cash flow metrics
- 5-year averages used for operational assumptions

**5-Year Forecast (FY2027E–FY2031E)**
- Revenue: $46.4B → $57.0B
- EBIT: $4.8B → $6.8B
- Unlevered Free Cash Flow: $3.4B → $4.9B

**Discounting**
- WACC-based discount factors
- Present value of each year's UFCF
- **Sum of PV of Forecast UFCFs: $15.7B**

**Terminal Value (Two Methods)**

1. **Gordon Growth Model**
   - TV = UFCF₅ × (1+g) / (WACC−g)
   - PV of TV: **$49.0B**
   - Implied Price: **$42.35**

2. **Exit Multiple Method**
   - TV = EBITDA₅ × Exit Multiple
   - PV of TV: **$75.0B**
   - Implied Price: **$59.91**

**Valuation Bridge**
- Enterprise Value → Less Net Debt → Equity Value → ÷ Shares → **Implied Price**

**Sensitivity Analysis**
- 7×7 sensitivity tables for both methods
- WACC range: Base ± 1.5%
- Terminal growth: 1.0% to 4.0%
- Exit multiple: 11.0x to 17.0x

---

## 🎨 Key Features

### Professional Modeling Standards

- **Color-coded inputs**: Blue text + yellow fill = editable; Black = formulas; Green = cross-sheet links
- **Consistent formulas**: Same calculation logic across all forecast periods
- **No circular references**: Clean, auditable formula structure
- **Proper formatting**: Currency, percentages, multiples formatted correctly
- **Documentation**: Every assumption sourced and explained inline

### Best Practices

- Market-value weighted WACC (not book value)
- Unlevered free cash flow approach (enterprise value method)
- Multiple terminal value methods for valuation range
- Sensitivity analysis for key drivers
- Historical context (5 years of actuals)

### Excel Formula Examples

**WACC Calculation:**
```excel
=(E/V × Ke) + (D/V × Kd × (1−Tax Rate))
```

**Unlevered Free Cash Flow:**
```excel
=NOPAT + D&A − CapEx − ΔNWC
where NOPAT = EBIT × (1 − Tax Rate)
```

**Gordon Growth Terminal Value:**
```excel
=UFCF₅ × (1 + g) / (WACC − g)
```

---

## 💡 Methodology

### Revenue Forecasting
Gradual recovery from FY2026's depressed growth (0.2%), accelerating to 5% by FY2029E, then normalizing to 4% by FY2031E. Reflects brand strength recovery and market normalization.

### EBIT Margin Recovery
Starting at 10.0% in FY2027E and expanding to 12.0% by FY2031E. Assumes operational leverage, cost management, and return toward Nike's historical 5-year average (~11.4%).

### Capital Assumptions
- **D&A:** 1.6% of revenue (5-year historical average)
- **CapEx:** 1.5% of revenue (5-year historical average)
- **NWC:** 1.0% of revenue (conservative estimate based on historical volatility)

### WACC Components
- **Risk-Free Rate:** 5.18% (10Y US Treasury as of Sept 25, 2026)
- **Beta:** 1.11 (5-year monthly, Yahoo Finance)
- **Equity Risk Premium:** 5.0% (Damodaran long-run estimate)
- **Cost of Debt:** Derived from FY2026 interest expense and total debt
- **Tax Rate:** 20.31% (FY2026 effective rate)
- **Weights:** Market-value based (82.7% equity, 17.3% debt)

### Terminal Value Approaches

1. **Gordon Growth (Conservative)**
   - Assumes perpetual 2.5% growth (long-run GDP/inflation proxy)
   - More conservative, lower implied value
   - Preferred for mature, stable businesses

2. **Exit Multiple (Market-Based)**
   - Assumes Nike trades at 15.0x EBITDA in Year 5
   - Based on historical trading range and peer comparables
   - Higher implied value, reflects market re-rating potential

---

## 📊 Data Sources

| Data Point | Source | Date |
|------------|--------|------|
| Historical Financials (FY22-26) | Nike.xlsx dataset | Company 10-K |
| Stock Price ($35.75) | Yahoo Finance | Sept 27, 2026 |
| Beta (1.11) | Yahoo Finance | 5Y Monthly |
| Risk-Free Rate (5.18%) | Yahoo Finance (^TNX) | Sept 25, 2026 |
| Equity Risk Premium (5.0%) | Damodaran | Standard estimate |

---

## 🔍 Interpretation & Investment Implications

### Valuation Range Analysis

Both valuation methods suggest Nike is **undervalued** at $35.75:
- **Conservative case (Gordon Growth):** $42.35 → **18.5% upside**
- **Base case (Exit Multiple):** $59.91 → **67.6% upside**

### Key Observations

**Strengths:**
- Both methods indicate positive upside
- Downside protection: Even at elevated WACC (10.5%) and low growth (1.5%), implied price near current market
- Margin recovery assumption appears reasonable given historical performance

**Risks:**
- Terminal value represents 75-83% of enterprise value (sensitive to assumptions)
- EBIT margin improvement required for base case to materialize
- Consumer discretionary exposure (economic cycle risk)
- FX headwinds not explicitly modeled

**Sensitivity Insights:**
- ±50bps change in WACC → ±$5-10 per share
- ±50bps change in terminal growth → ±$3-6 per share
- ±1x change in exit multiple → ±$4 per share

### Use Cases

✅ **Equity research & investment analysis**  
✅ **Financial modeling education**  
✅ **DCF methodology reference**  
✅ **Scenario analysis & stress testing**  
✅ **Peer comparison (adapt for other companies)**

---

## 🛠️ Customization Guide

### Adapting for Other Companies

1. **Update historical data** in Tab 2 (Historical Financials section)
2. **Adjust market inputs** in Tab 1 (price, beta, shares, debt)
3. **Modify forecast assumptions** based on company-specific drivers
4. **Revise terminal assumptions** (growth rate, exit multiple)
5. **Update documentation** (company name, sources, dates)

### Scenario Analysis

To create bull/bear scenarios:
1. Save multiple versions of the file
2. Adjust key assumptions in Tab 1:
   - Bull: Higher revenue growth, better margins, lower WACC
   - Bear: Lower growth, margin pressure, higher WACC
3. Document scenario rationale in assumptions tab

### Advanced Modifications

- Add quarterly forecasting (requires expanding forecast structure)
- Include working capital detail (A/R, inventory, A/P schedules)
- Model debt repayment schedule (currently uses static debt)
- Add Monte Carlo simulation (requires VBA or Python integration)
- Integrate with live market data feeds (Bloomberg, FactSet)

---

## ⚠️ Important Notes

### Excel Compatibility
- **Requires Microsoft Excel** for proper formula calculation
- LibreOffice Calc may have compatibility issues with some functions
- All formulas follow Excel 2016+ standards

### Model Limitations

1. **Static forecast:** Single base case scenario (use sensitivity for ranges)
2. **5-year explicit period:** Terminal value assumes perpetuity beyond
3. **No probabilistic analysis:** Deterministic model (no Monte Carlo)
4. **Simplified capital structure:** Does not model detailed debt schedule
5. **Mid-year convention not applied:** Cash flows discounted to year-end

### Disclaimer

This model is for **educational and analytical purposes only**. It should not be considered investment advice. Always:
- Verify assumptions against current market conditions
- Cross-check with other valuation methods (comparables, precedent transactions)
- Consider qualitative factors not captured in the model
- Consult with financial professionals for investment decisions

---

## 📚 Resources

### Further Reading

- **Valuation:** *Investment Valuation* by Aswath Damodaran
- **Financial Modeling:** *Financial Modeling* by Simon Benninga
- **DCF Analysis:** *Valuation: Measuring and Managing the Value of Companies* by McKinsey & Company
- **Excel Best Practices:** *Financial Modeling Best Practices* by F1F9.com

### Online Resources

- [Damodaran Online](http://pages.stern.nyu.edu/~adamodar/) - Cost of capital data, equity risk premiums
- [Yahoo Finance](https://finance.yahoo.com/) - Stock prices, beta, Treasury yields
- [SEC EDGAR](https://www.sec.gov/edgar) - Company filings (10-K, 10-Q)
- [FRED Economic Data](https://fred.stlouisfed.org/) - Macroeconomic data

---

## 🤝 Contributing

Contributions are welcome! If you'd like to improve the model:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes and test thoroughly
4. Commit with clear messages (`git commit -m 'Add sensitivity for tax rates'`)
5. Push to your branch (`git push origin feature/improvement`)
6. Open a Pull Request with a description of changes

**Suggestions for contributions:**
- Additional sensitivity analyses (tax rate, margin scenarios)
- Alternative terminal value methods (H-Model, Fade Model)
- Comparative company analysis tab
- Dashboard with charts and visualizations
- Documentation improvements

---

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 👤 Author

**Minal Khalid**

- GitHub: [@minal-khalid13](https://github.com/minal-khalid13)
- Repository: [DCF-Valuation-Model](https://github.com/minal-khalid13/DCF-Valuation-Model)

---

## 🙏 Acknowledgments

- Nike, Inc. for publicly available financial data
- Yahoo Finance for market data
- Aswath Damodaran for valuation methodology and equity risk premium data
- Financial modeling community for best practices

---

## 📧 Contact

For questions, suggestions, or issues:
- Open an issue in this repository
- Contact via GitHub profile

---

## 🔄 Version History

### v1.0.0 (September 27, 2026)
- Initial release
- Complete DCF model with dual terminal value methods
- Historical financials (FY2022-FY2026)
- 5-year forecast (FY2027E-FY2031E)
- WACC calculation and sensitivity analysis
- Comprehensive documentation

---

**⭐ If you find this model useful, please give it a star!**

---

*Built with Claude Code | September 2026*
