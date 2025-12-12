[FX Hedging Model] – Technical Specification
Created by: Frederick Tamayo Jr
Updated by: Frederick Tamayo Jr
Date Created: October 23, 2025
Date Updated: October 23, 2025
Version: 1.0

Role:
Financial Analyst / Treasury Analyst
Audience:
Chief Financial Officer / Director of Treasury

Purpose
Provide a quantitative modeling framework to evaluate FX hedge strategies designed to protect the USD value of a USD-denominated receivable that is economically exposed to EURUSD currency movements due to cost structure and margin reporting in USD.

1. Problem Statement
Our U.S. aerospace division expects to receive $20,000,000 USD in 12 months. Although the receivable is denominated in USD, our profitability and internal performance metrics are exposed to movements in EURUSD, since a large portion of production costs and competitive pricing benchmarks are euro-linked. If the USD appreciates (EUR weakens), competitive pressure could force price adjustments or margin compression, reducing the effective USD value to the business.
This specification defines the analytics required to evaluate hedging strategies that reduce foreign-exchange risk and protect expected dollar profitability.

2. Inputs (Known Variables)
Variable
Description
Unit
Example
Source
USD_AMT
USD receivable
USD
20,000,000
Company ERP
S₀
EURUSD spot rate
USD per EUR
1.174
Market
F₀
1-yr EURUSD forward
USD per EUR
1.0935
Provided
r_USD
USD 1-yr interest rate
%
4.25%
Market
r_EUR
EUR 1-yr interest rate
%
2.15%
Market
t
Time horizon
Years
1
Contract
K_put
EUR put strike
USD/EUR
1.174
Analyst
K_call
EUR call strike
USD/EUR
1.174
Analyst
Premium_put
Put premium
USD per EUR
0.019
Scenario
Premium_call
Call premium
USD per EUR
0.024
Scenario


3. Assumptions & Constraints
Interest rates are simple annual yields
Forward rate is 1-year maturity
No tax, transaction, or credit costs assumed
Option premiums paid upfront in USD
Hedge notional sized to economic exposure based on EUR-equivalent risk
FX quotes expressed USD per EUR


4. Calculation Flow (Model Logic)
Convert USD receivable into an implied EUR exposure using S₀
Compute hedge payoffs assuming varying EURUSD at maturity (S_T)
Forward hedge: lock USD via EUR synthetic hedge structure
Money-market hedge: borrow EUR → convert to USD → invest → repay with EUR equivalent exposure
Option hedges: evaluate EUR put (downside protection) and call (upside hedge)
Compare USD proceeds and effective rates under each hedge structure
Summarize trade-offs: cost, certainty, flexibility



5. Outputs
Output
Description
Format
Purpose
USD_forward
USD proceeds under forward hedge
Numeric
Benchmark for certainty
USD_mm
USD proceeds from money-market hedge
Numeric
Cross-check parity
USD_put
USD outcomes with EUR put
Table
Downside protection
USD_call
USD outcomes with EUR call
Table
Evaluate upside
Chart_1
Hedge payoff profiles
Line chart
Executive visualization
Summary
Written conclusion
1–2 paragraphs
CFO-level insight


6. Sensitivity Plan
Vary EURUSD rate (S_T) from 0.9×S₀ to 1.1×S₀ (increments of 0.01)
Calculate USD proceeds for each hedge at each S_T
Display results in:
Sensitivity matrix
Comparative payoff chart

7. Limitations & Next Steps
Volatility and real option pricing not yet incorporated


Assumes perfect market liquidity and no counterparty constraints


Next Step:
- Build the Excel model implementing this specification and test hedge outcomes (Stage 3)
