# quarto_paper_template

Template repository for quickly starting a Quarto-based paper project with a
main manuscript, supplementary document, custom LaTeX template, and Lua filters.

## Quick start

1. Clone this repository.
2. Update metadata in `_quarto.yml` (title, authors, affiliations, keywords).
3. Write your sections in `paper.qmd` and the included partial files.
4. Add supplementary content in `supplementary.qmd` and `_supplemental_info.qmd`.
5. Render with `quarto render`.

## Main files

- `_quarto.yml`: Project-level metadata, formats, and filters.
- `paper.qmd`: Main manuscript structure.
- `supplementary.qmd`: Supplementary document wrapper.
- `_preamble.tex`: Shared LaTeX preamble customizations.
- `template.tex`: Custom LaTeX template for PDF output.

## Lua filters included

- `tikz.lua`: Renders TikZ code blocks as figures.
- `abstract-filter.lua`: Maps `.abstract` content to LaTeX abstract environment.
- `strip-yaml-frontmatter.lua`: Removes leaked YAML from included fragments.
- `color-text-span.lua`: Preserves inline text colors in PDF output.
- `maintext-filter.lua`: Handles `.maintext` wrapper behavior by format.
- `sitext-filter.lua`: Handles `.sitext` wrapper behavior by format.
- `sitext-refsection.lua`: Creates a separate SI reference section in PDF.
