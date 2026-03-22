# Liquidity-Aware Machine Learning for Stock Return Prediction

LaTeX project for the paper (Overleaf-compatible).

## Structure

```
├── Main.tex              # Main paper
├── Appendix.tex          # Appendix (ML details, bootstrap, additional results)
├── preamble.tex          # Math macros and theorem environments
├── Biblio.bib            # References (apalike style)
├── Slides.tex            # Beamer presentation (Metropolis theme)
├── FiguresNew/           # Figures from 03_analyze_results.py
├── TablesNew/            # Table templates
│   ├── MainResults.tex
│   ├── NetResults.tex
│   ├── H2Summary.tex
│   └── FactorAlphas.tex
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

Table templates use placeholder `0.00` values. Replace with actual results from:
- `outputs/experiment/{model}/effect_decomposition.json`
- `outputs/analysis/tables/main_results.csv`
- `outputs/analysis/tables/net_results.csv`
- `outputs/analysis/tables/h2_summary.csv`
- `outputs/analysis/tables/factor_alphas.csv`

## Adding Figures

Copy figures from `outputs/analysis/figures/` into `FiguresNew/`, then uncomment the `\includegraphics` lines in `Main.tex`.
