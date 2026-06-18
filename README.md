# Estonian OÜ Salary Calculator

A simple, single-page calculator for estimating your **take-home pay** from an Estonian
private limited company (OÜ), when you pay yourself with a mix of **monthly salary** and
**dividends** (paid out yearly or bi-yearly).

👉 **Live:** https://th0masl.github.io/estonia-ou-salary-calculator/

Everything runs in your browser — no backend, no tracking, no data leaves your machine.

## What it does

You enter:

- the **annual amount billed** by your OÜ (the revenue available to pay out), and
- the **share paid as salary** (the rest goes to dividends).

It shows the full breakdown — employer taxes, gross/net wage, dividend tax — and your
**final yearly and monthly take-home**, plus your effective tax & contribution rate.

Options:

- **Basic exemption** — the 2026 flat €700/mo (€8,400/yr) tax-free allowance.
- **EE client** — adds the 24% VAT line to your invoice (pass-through, doesn't affect take-home).
- **Pension on 100% dividends** — when salary is 0%, adds the minimum social tax + optional 6% pension.

## Tax rates (2026)

All rates live in the `R = { ... }` object near the top of the `<script>` in
[`index.html`](index.html) — edit there to update for a new tax year.

| Item | Rate |
|---|---|
| Employer social tax | 33% |
| Employer / employee unemployment | 0.8% / 1.6% |
| Funded pension (II pillar) | 2% |
| Personal income tax | 22% |
| Dividend tax (22/78 system) | 22% of gross |
| Basic exemption | €8,400 / yr |
| VAT (EE clients only) | 24% |

## Run locally

It's a single static file — just open `index.html` in a browser, or serve it:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Disclaimer

Estimates only, based on Estonian tax rules effective 2026. The funded pension (II pillar)
is your own savings, shown as a deduction from take-home cash. This is **not tax advice** —
verify with the [Estonian Tax and Customs Board](https://www.emta.ee/en) or your accountant.
