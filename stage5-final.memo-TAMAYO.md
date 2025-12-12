Stage 5 – Final Analysis & Recommendation Memo

FX Hedging Analysis for EUR Receivable

Prepared by: Frederick Tamayo Jr
Role: Financial Analyst / Treasury Analyst
Date: 12/12/25

A. Exposure Summary

The firm expects to receive a €20,000,000 receivable in one year from a European customer. Because the firm reports in USD, the value of this receivable is exposed to fluctuations in the EUR/USD exchange rate. If the euro depreciates relative to the dollar before settlement, the USD value of the receivable will decline, negatively affecting cash flow, margins, and budgeted revenue. Conversely, euro appreciation would increase USD proceeds but introduces volatility into financial planning. This exposure creates uncertainty in reported earnings and complicates treasury forecasting.

B. Summary of Hedge Outcomes

Three hedge strategies were evaluated using the Stage 3–4 Excel model:

Forward Hedge: Locks in USD proceeds using the 1-year forward rate (1.0935). This produces a fixed USD outcome regardless of future spot movements.

Money Market Hedge: Replicates the forward hedge by borrowing euros, converting at spot, and investing USD. Results closely match the forward hedge, confirming interest rate parity.

Option Hedges (Put & Call):

The EUR put option provides downside protection if the euro weakens, while allowing upside participation if the euro strengthens.

The EUR call option benefits from euro appreciation but is less suitable for protecting downside risk on a receivable.

Both options incur an upfront premium, reducing net proceeds in stable or favorable scenarios.

The forward and money market hedges offer certainty, while options trade certainty for flexibility.

C. Sensitivity Interpretation

EUR Depreciation:
The forward and money market hedges outperform by fully protecting USD proceeds. The put option limits losses but still reflects premium cost.

EUR Appreciation:
Options outperform fixed hedges due to upside participation. The forward and MM hedges forego gains.

Trade-off:
Certainty vs. flexibility. Fixed hedges eliminate volatility; options retain upside at a cost.

D. Strategic Recommendation

Recommended Strategy: Forward Hedge (Primary Choice)

Given the firm’s priority on cash-flow stability, budget certainty, and risk reduction, the forward hedge is the most appropriate strategy. It eliminates FX uncertainty at minimal cost and aligns with conservative treasury policy.

A partial option overlay (e.g., 80% forward / 20% put) could be considered if management desires limited upside participation without materially increasing risk.

E. Executive Justification

Ensures predictable USD cash flows

Simplifies budgeting and earnings guidance

Requires no premium or complex monitoring

Strong alignment with corporate risk-management objectives

Extra Credit – Areas for Further Study & Improvement
1. Claude Skills (Automation & Live Data Integration)

A Claude Skill could automatically pull live FX spot rates, forward curves, and interest rates, update the model daily, regenerate spreadsheets on demand, and produce instant executive summaries. This would reduce manual updates and improve decision speed.

2. OpenAI Codex / Code Interpreter

Codex could convert the Excel logic into Python, validate formulas, and run Monte Carlo simulations on EUR/USD paths. This would enhance risk analysis and reduce model error and operational risk.

3. Claude Code / Multi-File Reasoning

Claude’s multi-file reasoning could maintain consistency across specifications, Excel models, and memos, automate version control, and rebuild models end-to-end. This improves auditability and governance across the FX hedging workflow.
