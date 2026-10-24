# Building the English report

Upload the complete project ZIP to Overleaf using New Project → Upload Project. Select `report/main.tex` as the main document and use pdfLaTeX. If Overleaf retains the outer repository folder, include it in the main-document path.

For a smaller Overleaf project, retain `report/main.tex`, its complete `figures/` folder, and the sibling `matlab/allstates.m` file. The report imports that code listing. Native COMSOL models and other data exports are not needed for compilation.

Local TeX Live or MiKTeX: from the repository root, change to `report/` and run `pdflatex -interaction=nonstopmode -halt-on-error main.tex` twice. A further pass may be needed if longtable column widths change.

The report uses standard packages, including amsmath, graphicx, listings, longtable, and Latin Modern fonts. No custom fonts, `.bib`, `.cls`, or `.sty` files are required. Typesetting does not execute MATLAB or COMSOL.
