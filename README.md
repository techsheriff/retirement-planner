# Retirement Monte Carlo Planner

A single-page retirement calculator for US investors. Enter your age, savings,
spending, and Social Security estimate; it runs 10,000 Monte Carlo simulations
in your browser and tells you whether your plan clears a confidence bar you
choose (85% by default), what you'd need to save or hold to clear it, and how
sensitive the answer is to retiring earlier or spending more.

**Live version:** https://techsheriff.github.io/retirement-planner/

## What it shows

- A pass/fall-short verdict against your confidence level
- A fan chart of portfolio balance by age across all 10,000 simulated futures,
  with the worst-case planning path highlighted
- The portfolio size you need on retirement day, the yearly savings required
  to get there, and the maximum spending your plan supports
- A sensitivity grid: success rates across retirement ages and spending levels
- When failing paths run out of money, and a printable list of every
  assumption used

## Privacy

Everything runs in your browser. The page makes no network requests, so
nothing you type is transmitted anywhere. Entries are kept in your browser's
local storage on your own device; the "Reset all data" button erases them.

## Model and defaults

All amounts are in today's dollars; returns are real (after-inflation)
returns, so inflation never needs to be entered. Defaults are deliberately
conservative: 5% real stock returns (below the ~7% historical average), 1.5%
real bond returns, a portfolio that glides from 80% stocks to 60% by
retirement, a 12% blended tax rate on withdrawals, and a 20% haircut on Social
Security benefits for trust-fund uncertainty. All of these can be changed
under Economic Assumptions.

## Caveats, including the AI one

This tool was built with substantial help from an AI assistant (Anthropic's
Claude), with human review and testing. The simulation engine was validated
against an independently written reference implementation, and the page has
been through a security and accessibility review. Even so: AI-assisted code
can contain mistakes that review missed. Read the numbers skeptically.

It is an educational model, not financial advice, and it simplifies reality
in ways that matter:

- Returns are drawn as independent normal years. Real markets have fat tails
  (crashes come more often than a bell curve predicts), so bad outcomes are
  somewhat more likely than the simulation shows.
- Taxes use one blended rate. Real tax sequencing (RMDs, brackets, IRMAA,
  Roth conversions) can make your situation better or worse.
- Spending is flat in real terms for life. No long-term-care shock, no
  late-life spending decline.
- Social Security figures are whatever you type in. Get the real number from
  ssa.gov/myaccount, and remember the statement assumes you keep working
  until you claim.

Before acting on anything this tool tells you, check the plan with a
fee-only fiduciary advisor or at minimum against an independent tool
(cFIREsim, FICalc, TPAW Planner) to see whether the answers agree.

## Running locally

It's one file. Clone the repo and open `index.html` in a browser, or serve it
with any static server (`python3 -m http.server`).

## License

MIT. See [LICENSE](LICENSE).
