Stage 4 – Structured AI Prompt (Prompt Engineering Deliverable)

You are a financial modeling assistant supporting a corporate treasury team.

# GOAL

Create a fully functional Excel (.xlsx) FX hedging model that evaluates forward, money market, and option hedges for a EUR-denominated receivable, using real market inputs and professional treasury modeling standards.

The spreadsheet must be executive-ready, auditable, and suitable for CFO review.

# CONTEXT

Translate the modeling logic from my Stage 2 specification and Stage 3 Excel logic into a new, complete, professional spreadsheet
- https://github.com/fftamayo/FIN321_Github/blob/main/stage2-spec-tamayo.md
- https://github.com/fftamayo/FIN321_Github/stage3-.xlsx

# INPUT VARIABLES (Scenario-Specific — All Values Explicit)

Use the following inputs exactly as provided:

FC_AMT = 20,000,000 EUR

S0_in (Spot EURUSD) = 1.1740 USD/EUR

F0_in (1Y Forward EURUSD) = 1.0935 USD/EUR

R_USD (USD 1Y interest rate) = 4.25%

R_FC (EUR 1Y interest rate) = 2.15%

K_PUT = 1.1740 USD/EUR

K_CALL = 1.1740 USD/EUR

PREM_PUT = 0.019 USD per EUR

PREM_CALL = 0.024 USD per EUR

T_DAYS = 360

T_YRS = T_DAYS / 360

All values must be hard-coded into the model inputs (not inferred).

# SPREADSHEET REQUIREMENTS
1. Named Ranges (Mandatory)

Define and use only the following standardized names:

FC_AMT

S0_in

F0_in

R_USD

R_FC

K_PUT

K_CALL

PREM_PUT

PREM_CALL

T_DAYS

T_YRS

Do not invent alternative names.

2. Formatting & Color Coding (Strict)

Apply consistent formatting:

Yellow → Inputs / decision variables

Blue → Assumptions

Green → Formula cells

Gray → Outputs / KPIs

Use clearly labeled sections and readable layout.

# MODEL COMPONENTS (Required)
A. Forward Hedge

Compute locked-in USD proceeds:
USD_forward = FC_AMT × F0_in

Display clearly in the comparison section.

B. Money Market Hedge (3-Step)

Show each step explicitly:

Borrow EUR today

Convert borrowed EUR to USD at S0_in

Invest USD at R_USD for T_YRS

Repay EUR loan at maturity using receivable.

Final USD proceeds must be shown.

This result should closely match the forward hedge (interest parity check).

C. Option Hedges

Include both:

EUR Put Option

Payoff: max(K_PUT − S_T, 0) × FC_AMT − total premium

EUR Call Option

Payoff: max(S_T − K_CALL, 0) × FC_AMT − total premium

Show:

Total premium paid

USD proceeds under varying S_T

D. Sensitivity Table (±5%)

Create a sensitivity analysis where:

S_T varies from 0.95 × S0_in to 1.05 × S0_in

Increment = 1%

For each S_T, compute USD proceeds for:

Forward

Money Market

Put Option

Call Option

(Optional but encouraged): include a line chart comparing outcomes.

# MODEL LOGIC (PSEUDOCODE)

S_T = sequence(0.95*S0_in , 1.05*S0_in , step=0.01)
USD_unhedged = FC_AMT * S_T

Forward:
  USD_forward = FC_AMT * F0_in

Money Market:
  EUR_borrow = FC_AMT / (1 + R_FC*T_YRS)
  USD_invest_0 = EUR_borrow * S0_in
  USD_MM = USD_invest_0 * (1 + R_USD*T_YRS)

Put Hedge:
  Premium_PUT_total = FC_AMT * PREM_PUT
  Payoff_PUT = max(K_PUT - S_T, 0) * FC_AMT
  USD_PUT_SCEN = if(S_T < K_PUT,
                     FC_AMT*K_PUT - Premium_PUT_total,
                     FC_AMT*S_T - Premium_PUT_total)

Call Hedge:
  Premium_CALL_total = FC_AMT * PREM_CALL
  Payoff_CALL = max(S_T - K_CALL, 0) * FC_AMT
  USD_CALL_SCEN = (FC_AMT*S_T + Payoff_CALL) - Premium_CALL_total


# OUTPUT REQUIREMENTS

The spreadsheet must include:

Forward hedge USD result

Money market hedge USD result

Option hedge results across sensitivity scenarios

A summary section suitable for executive interpretation

# VERIFICATION (MANDATORY)

You must:

Validate parity between forward and money market hedges

Confirm all named ranges exist and are used correctly

Provide a formula map or clear traceability for audit review

# EXPORT

Return a downloadable Excel (.xlsx) file containing the completed model with all calculations, formatting, and verification checks implemented.
