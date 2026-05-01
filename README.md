# Liquidity-Aware Machine Learning for Stock Return Prediction

LaTeX project for the paper (Overleaf-compatible).

## Structure

```
├── Main.tex              # Main paper
├── Appendix.tex          # Appendix (ML details, bootstrap, additional results)
├── preamble.tex          # Math macros and theorem environments
├── Biblio.bib            # References (apalike style)
├── Slides.tex            # Beamer presentation (Metropolis theme)
├── FiguresNew/           # Figures from 21a-21e_formal_*.py
├── TablesNew/            # Table templates (regenerate from formal analysis CSVs)
├── .gitignore
└── README.md
```

## Compilation

```bash
pdflatex Main
bibtex Main
pdflatex Main
pdflatex Main
```

Or: `latexmk -pdf Main`

## Populating Tables

Table templates pull values from the formal analysis CSVs under
`outputs/formalanalysis/analysis/{model}/{weight_spec}/`:

- `r2_by_quintile.csv`                    — 21a: OOS R² per liquidity quintile (M_std vs M_w)
- `utility_weighted_r2.csv`               — 21a: utility-weighted R² gap
- `importance_shift.csv`                  — 21b: per-feature SHAP delta with paired t-stat
- `gamma_regression.json`                 — 21b: regression of Δ-importance on Step 2 γ
- `delta_gamma.csv`                       — 21b: feature-level (γ̄, Δ) data underlying that regression
- `group_shares.csv`                      — 21b: importance shares by Q1-only / Q5-only / both / neither
- `restriction_curve_comparison.csv`      — 21c: weighted model vs hard-restriction curve on Q4–Q5
- `liquid_squared_error_differential.csv` — 21d: monthly SE differential on Q4–Q5
- `two_by_two_{aum}.csv`                  — 21e: 2×2 decomposition at each AUM ($10M / $100M / $500M / $1B)
- `within_quintile_portfolio.csv`         — 21e: within-quintile gross/net SR at the primary AUM

Top-level summary at `outputs/formalanalysis/analysis/formal_hypothesis_tests.json`
holds the H1 / H3 hypothesis-test statistics and Sharpe-ratio decomposition at the primary AUM.

## Adding Figures

Copy figures from `outputs/formalanalysis/analysis/{model}/{weight_spec}/*.png` into
`FiguresNew/`, then uncomment the `\includegraphics` lines in `Main.tex`. See
`FiguresNew/README.md` for the list of expected figures.
