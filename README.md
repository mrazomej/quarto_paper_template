# quarto_paper_template
This repository contains the basic files used to put together a scientific
publication as a PDF and an HTML using Quarto


## How to use this template

1. Clone this repository
2. Edit the `_quarto.yml` file to include your metadata
3. Edit the `paper.md` file to include your content
4. Run `quarto render` to render the PDF and HTML files
5. Enjoy!

## Main Files

- `_quarto.yml`: Metadata for the paper
- `paper.md`: The content of the paper
- `_preamble.tex`: LaTeX preamble for the paper with some formatting
  instructions
- `template.tex`: custom LaTeX template for the paper

## Lua Filters

- `color-text-span.lua`: Lua filter to color text spans in the paper.
    - In essence, this filter allows users to write documents with HTML-style
      colored text (using inline styles), and when converting to LaTeX, it
      automatically translates these into appropriate LaTeX color commands. This
      ensures that colored text in the source document is preserved and properly
      rendered in the LaTeX output.
- `maintext-filter.lua`: Lua filter to process the main text of the paper.
    - This filter allows for different handling of the 'maintext' div in
      different output formats. In LaTeX, it adds specific LaTeX commands to
      handle references and formatting, while in HTML, it removes the div
      wrapper but keeps the content.
- `sitext-filter.lua`: Lua filter to process the side text of the paper.
    - This filter allows for special handling of a 'supplemental information'
      section. When outputting to LaTeX, it adds necessary LaTeX commands to
      properly format this section. For HTML output, it removes the div wrapper
- `sitext-refsection.lua`: Lua filter to process the side text of the paper.
    - This Pandoc Lua filter enhances the presentation of supplemental
      information (SI) in academic documents. It targets content within <div
      class="sitext"> elements, applying specific formatting for LaTeX and HTML
      outputs. For LaTeX, it creates a custom environment with a table of
      contents, proper numbering, and a separate bibliography for the SI
      section. In HTML, it simply removes the div wrapper, allowing for custom
      styling via CSS. This filter streamlines the process of including
      supplemental material in academic papers, ensuring consistent and
      professional formatting across different output formats.

### Using `maintext-filter.lua` and `sitext-filter.lua`

To use these filters, you need to add the `maintext` or `sitext` class to the
divs you want to format.

`maintext-filter.lua` usage:

Place your main text within a div with the class "maintext" in your Markdown document:

```
::: {.maintext}
Your main text here...
:::
```

`sitext-filter.lua` usage:

Place your supplemental information within a div with the class "sitext" in your Markdown document:

```
::: {.sitext}
Your supplemental content here...
:::
```