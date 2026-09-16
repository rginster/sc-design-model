# Battery Supply Chain Design — Pareto Explorer

An interactive, self-contained explorer for the Pareto front of a battery cell supply
chain design model. The model decides where the materials for an NMC811 battery cell
are extracted and refined and where cathode material and cells are produced and
recycled. It weighs three objectives against each other: total cost, climate change and
risk of forced labor.

**Live version:** <https://rginster.github.io/sc-design-model/>

## Contents

`index.html` is the entire application: HTML, CSS and JavaScript in one file, with the
optimization results embedded and no external resources, libraries or network access.
Open it in any browser, or serve it from any static host. It works offline and on
mobile. The optimization model and its input data are not part of this repository.

## Features

- Two sliders for the ε-bounds on climate change and forced labor risk, plus buttons
  for the cost, climate and forced labor optimum and the status quo
- 3D Pareto front with rotation, 2D projections with non-dominated envelopes and the
  ε-grid as a heatmap; hover for values, click to select a solution
- Filter for practically efficient solutions
- Side-by-side world maps comparing two supply chain networks, with a stage filter and
  a table of each country's share per product
- Documentation of the model, the solution method, the validation and the data
- English and German interface (English by default), light and dark color scheme
- CSV export of the grid and of the activity levels

## Model

Activity-analysis linear program with 650 activities (23 processes in up to 95
countries). Total cost is minimized; climate change and risk of forced labor enter as
ε-constraints. Each bound runs in steps of 1 % from “no bound” to the best achievable
value, which gives 10,201 grid points and 1,731 distinct Pareto-optimal supply chains.
Ties are broken lexicographically, so every solution is Pareto-optimal. The results
were cross-checked with the augmented ε-constraint method (AUGMECON) and validated
independently of the solver. The status quo shows the current market supply chain for
comparison; it is not a feasible solution of the model.

## Sources

- Mavrotas, G. (2009). Effective implementation of the ε-constraint method in
  multi-objective mathematical programming problems. *Applied Mathematics and
  Computation*, 213(2), 455–465. https://doi.org/10.1016/j.amc.2009.03.037
- Thies, C., Kieckhäfer, K., & Spengler, T. S. (2021). Activity analysis based modeling
  of global supply chains for sustainability assessment. *Journal of Business
  Economics*, 91(2), 215–252. https://doi.org/10.1007/s11573-020-01004-x
- Map data: Natural Earth 1:110m land (public domain), via the npm package world-atlas.

## License

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

© 2026 Raphael Ginster. This work is licensed under a
[Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/)
(CC BY 4.0). You are free to share and adapt the material for any purpose, including
commercially, as long as you give appropriate credit, provide a link to the license and
indicate if changes were made. The full legal code is in [`LICENSE`](LICENSE).
