# Final Run Report

Run timestamp: 2026-05-21T03:38:23

## Environments
- Notebooks 01, 02, 03, 05, 06: ai-classic-ml-cpu.
- Notebook 04: ai-pytorch-mps.

## Final Notebook 06 Display Protocol
All wide result tables are decomposed into metric-family blocks and rendered through full HTML tables. The notebook output avoids truncated wide tables with hidden columns. Final figures were checked and reformatted for long-label readability, legend placement, annotation visibility, and publication-ready layout.

## Coordinate Protocol
Raw bus coordinates were retained as metadata only and excluded from trainable feature matrices.

## Architecture Diagram Revision
- Updated the two-page Draw.io architecture file using the existing `ai-classic-ml-cpu` conda environment.
- Page 1 was reformatted with additional internal list padding, clearer feature/target wording, and explicit feature-engineering links.
- Page 2 was simplified into the internal B-TGPRF architecture only, with mathematical block definitions and non-overlapping directed flow.
- A second visual QA pass was completed from exported PNG previews. Page 1 list text was physically inset inside list containers, and Page 2 was rebuilt in a compact non-wide architecture layout to improve readability and remove overlapping or excessively long arrows.
- A final visual QA pass simplified Page 2 from a formula-heavy architecture to a component-level B-TGPRF view. Page 1 list containers were rebuilt as stable list-style blocks after Draw.io stack layout caused row overlap during export.
