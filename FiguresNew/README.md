## Figures Directory

Place output figures from the step-level formal analysis scripts (`21a-21e_formal_*.py`) here.

### Expected figures

One of each is produced per `(model, weight_spec)` pair under
`outputs/formalanalysis/analysis/{model}/{weight_spec}/`:

- `importance_reallocation.png`           — 21b: top-30 SHAP reallocation (M_w − M_std)
- `restriction_curve_comparison.png`      — 21c: weighted model overlaid on Step 3d hard-restriction curve (Q4–Q5 R²)
- `liquid_squared_error_differential.png` — 21d: cumulative SE(M_std) − SE(M_w) on Q4–Q5 over time

21a (liquid-stock R² tables) and 21e (portfolio decomposition) produce CSV/JSON only.
