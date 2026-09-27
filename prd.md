DocumentProject Requirements — DCF Valuation Model

Subject CompanyNike, Inc. (NYSE: NKE)

Prepared forMinal — Finance Portfolio Project

Version1.0

StatusDraft — for build

# DCF Valuation Model — Project Requirements Document

A complete specification for building a discounted cash flow valuation of Nike, Inc. from scratch — data, methodology, deliverable format, and acceptance criteria.

1. [Project Overview](#overview)
2. [Objectives](#objectives)
3. [Scope](#scope)
4. [Data Requirements & Sources](#data)
5. [Methodology](#methodology)
6. [Assumptions Register](#assumptions)
7. [Deliverable Specification](#deliverable)
8. [Quality & Acceptance Criteria](#qa)
9. [Presentation Requirements](#presentation)
10. [Timeline & Milestones](#timeline)
11. [Known Limitations & Risks](#limitations)

## 1.Project Overview

Build a full discounted cash flow (DCF) model to estimate the intrinsic value of one share of Nike, Inc. common stock, from public/company-reported financial data through an explicit forecast, discounting, and terminal value process, ending in an implied per-share valuation and a defensible sensitivity range.

This project is one of three portfolio pieces (alongside a Comparable Company Analysis and a Three-Statement Financial Model) intended to demonstrate core valuation and modeling competency for finance coursework and interviews.

## 2.Objectives

- Produce an intrinsic value per share for NKE, independent of its current market price.
- Demonstrate the full mechanical chain: historical financials → forecast assumptions → unlevered free cash flow → discounting → terminal value → enterprise value → equity value → per-share price.
- Make every assumption explicit, sourced, and adjustable — no hardcoded outputs.
- Cross-check the terminal value under two independent methods (Gordon Growth and Exit Multiple).
- Stress-test the output with a WACC × terminal growth sensitivity grid.
- Be presentable and defensible to a finance-literate reviewer without notes.

## 3.Scope

### In scope

- Single-company DCF for Nike (NKE), consolidated entity level (no segment-level modeling).
- 5 years of historical financials (FY2022–FY2026) as the base.
- 5-year explicit forecast period (FY2027E–FY2031E).
- WACC build from first principles (CAPM cost of equity + after-tax cost of debt).
- Terminal value under Gordon Growth and Exit Multiple methods.
- Sensitivity table on WACC and terminal growth rate.

### Out of scope

- Segment-level (geography/channel) revenue build.
- Scenario/case modeling (bull/base/bear) beyond the sensitivity grid.
- Monte Carlo or probabilistic simulation.
- Comparable company or precedent transaction analysis (separate project).

## 4.Data Requirements & Sources

| Item | Detail | Source |
| --- | --- | --- |
| Income Statement | Revenue, COGS, SG&A, EBIT, tax expense, net income — FY2022–FY2026 | Uploaded Nike financials, Sheet1 |
| Balance Sheet | Cash, short-term investments, total debt, shares outstanding — FY2022–FY2026 | Uploaded Nike financials, Sheet2 |
| Cash Flow Statement | D&A, CapEx, change in net working capital — FY2022–FY2026 | Uploaded Nike financials, Sheet3 |
| Risk-free rate | 10-Year US Treasury yield | Live market data at valuation date |
| Beta | NKE levered beta | Google Finance |
| Current share price | NKE last traded price | Live market data at valuation date |

## 5.Methodology

### 5.1 Discount rate (WACC)

Cost of Equity = Risk-Free Rate + Beta × Equity Risk Premium Pre-Tax Cost of Debt = Interest Expense ÷ Total Debt After-Tax Cost of Debt = Pre-Tax Cost of Debt × (1 − Tax Rate) WACC = (E/V × Cost of Equity) + (D/V × After-Tax Cost of Debt)

Where E = market capitalization (share price × diluted shares), D = total debt, V = E + D.

### 5.2 Free cash flow build (per forecast year)

Revenue(t) = Revenue(t-1) × (1 + Growth Assumption) EBIT(t) = Revenue(t) × EBIT Margin Assumption NOPAT(t) = EBIT(t) × (1 − Tax Rate) UFCF(t) = NOPAT(t) + D&A(t) − CapEx(t) − Δ NWC(t)

D&A, CapEx and Δ NWC are each driven off a % of revenue assumption, benchmarked to the 5-year historical average of that ratio.

### 5.3 Discounting

Discount Factor(t) = 1 / (1 + WACC)^t PV of UFCF(t) = UFCF(t) × Discount Factor(t)

### 5.4 Terminal value

Gordon Growth: TV = UFCF(final year) × (1 + g) / (WACC − g) Exit Multiple: TV = EBITDA(final year) × Exit EV/EBITDA Multiple PV of TV = TV × Discount Factor(final year)

### 5.5 Enterprise value to share price

Enterprise Value = Σ PV(UFCF, all forecast years) + PV(Terminal Value) Equity Value = Enterprise Value − Net Debt Implied Price = Equity Value ÷ Diluted Shares Outstanding

Net Debt = Total Debt − Cash & Short-Term Investments, taken from the latest actual fiscal year.

## 6.Assumptions Register

Every assumption below must live in its own labeled, colored input cell in the deliverable — never buried inside a formula.

| Assumption | Basis | Type |
| --- | --- | --- |
| Risk-free rate | Current 10-Yr US Treasury yield | Market input |
| Equity risk premium | Standard long-run estimate (\~5%) | Market convention |
| Beta | NKE levered beta, live source | Market input |
| Tax rate | Most recent effective tax rate | Company-reported |
| Revenue growth (FY27–31) | Analyst judgment — gradual recovery post-decline | Judgment call |
| EBIT margin (FY27–31) | Analyst judgment — recovery toward historical average | Judgment call |
| D&A / CapEx / Δ NWC (% revenue) | 5-year historical average | Historical benchmark |
| Terminal growth rate (g) | Long-run GDP/inflation proxy (\~2–2.5%) | Convention |
| Exit EV/EBITDA multiple | Broadly in line with historical trading range | Judgment call, cross-check against Comps project |

## 7.Deliverable Specification

- **Format:** Excel workbook (.xlsx), formulas live (not hardcoded results), fully recalculating.
- **Tab 1 — Assumptions:** WACC build, capital structure, terminal value inputs, share count.
- **Tab 2 — DCF Model:** historicals, forecast, discounting, terminal value, valuation summary, sensitivity grid.
- **Color convention:** blue = hardcoded input, black = formula, green = cross-sheet link.
- **Every hardcoded number** carries a source note (company filing, market data provider, or "assumption").
- **Units:** $ in millions throughout, except per-share figures.

## 8.Quality & Acceptance Criteria

- Workbook recalculates with zero formula errors.
- Every forecast cell derives from an assumption cell — no year-over-year formula drift.
- Two independent terminal value methods both present, both reconciled to an implied share price.
- Sensitivity grid covers at minimum a ±1% range on both WACC and terminal growth rate.
- Implied share price is sanity-checked against the current trading price with a stated variance.
- Every input a reviewer would ask "where did that come from?" has a visible, one-line answer.

## 9.Presentation Requirements

1. Open with the investment narrative in one sentence, not the spreadsheet.
2. Walk top-down: WACC → forecast logic → terminal value → implied price.
3. Proactively name the model's weakest assumptions before being asked.
4. Defend the range (via the sensitivity table), not the single point estimate.
5. Be able to justify WACC and every forecast assumption from memory.

## 10.Timeline & Milestones

| Milestone | Deliverable |
| --- | --- |
| 1. Data collection | Historical financials assembled, sourced, verified |
| 2. WACC build | Assumptions tab complete, WACC finalized |
| 3. Forecast build | Revenue through UFCF projected, formulas live |
| 4. Valuation | Discounting, terminal value, implied share price |
| 5. Stress test | Sensitivity grid complete |
| 6. Narrative | Written explanation of assumptions and results |
| 7. Review | Mock presentation / defense of assumptions |

## 11.Known Limitations & Risks

- Cost of debt derived from blended embedded interest rate, not current marginal borrowing cost — likely understates true cost of new debt.
- Single-scenario forecast (no bull/bear cases) beyond the WACC/growth sensitivity grid.
- Revenue and margin recovery assumptions are judgment calls with no analyst consensus benchmark applied.
- Terminal value methods can diverge materially — the gap itself should be discussed, not hidden.
- Model reflects a single valuation date; all market inputs (price, yield, beta) will drift over time.

