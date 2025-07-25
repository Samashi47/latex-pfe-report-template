# LaTeX Template for PFE Report

## Description

This LaTeX template is specifically designed for creating professional PFE (Projet de Fin d'Études / End-of-Studies Project) reports for FSTT (Faculty of Sciences and Technology of Tangier). It provides a structured format that follows academic standards while offering flexibility for customization. The template includes pre-configured sections, proper formatting, and necessary packages to create a comprehensive academic report.

This is the template I used for my own master thesis, and I am happy to share it with you to help you create your own reports efficiently and without the hassle of setting up everything from scratch, as LaTeX can be quite complex for beginners. This template aims to simplify the process while maintaining a professional appearance.

## Features

- Professional document structure suitable for academic reports
- Pre-configured title page, table of contents, and bibliography
- Integrated UML diagram support via tikz-uml package
- Proper sectioning and formatting for academic writing
- Bibliography management with BibTeX
- Cross-referencing capabilities for figures, tables, and equations
- Customizable styling and layout options

## Requirements

- LaTeX distribution (TeX Live, MiKTeX, or MacTeX)
- pdfLaTeX compiler
- tikz-uml.sty package (included in template)

## How to Use

### Option 1: Using Overleaf (Recommended)
1. Upload all template files to a new Overleaf project
2. Edit the main .tex file with your content
3. Compile to generate your PDF report

### Option 2: Local Installation
1. Clone or download this repository
2. Ensure you have a LaTeX distribution installed
3. Compile using pdfLaTeX:
   ```bash
   pdflatex main.tex
   bibtex main
   pdflatex main.tex
   pdflatex main.tex
   ```

### Option 3: VS Code with MiKTeX (Windows)
For users using VS Code with MiKTeX on Windows, we recommend adding the following configuration to your `settings.json` to keep auxiliary files in a temporary folder for a cleaner workspace:

```json
"latex-workshop.latex.tools": [
    {
        "name": "pdflatex",
        "command": "pdflatex",
        "args": [
        "-aux-directory=tmp",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
        ],
        "env": {}
    },
    {
        "name": "bibtex",
        "command": "bibtex",
        "args": [
        "--include-directory=tmp",
        "tmp/%DOCFILE%"
        ],
        "env": {}
    }
]
```

This configuration ensures that auxiliary files generated during compilation are stored in a `tmp` folder, keeping your project directory clean.

## What is tikz-uml.sty?

The `tikz-uml.sty` package is a LaTeX style file that provides commands for creating UML (Unified Modeling Language) diagrams directly within your LaTeX document. This package is built on top of TikZ and PGF, offering:

- **Class diagrams**: Create professional UML class diagrams with proper notation
- **Sequence diagrams**: Design interaction diagrams showing message flow
- **Use case diagrams**: Illustrate system functionality and user interactions
- **Component diagrams**: Display system architecture and dependencies
- **Customizable styling**: Adjust colors, fonts, and layout to match your document

The tikz-uml package is particularly useful for software engineering and computer science PFE reports where UML diagrams are essential for documenting system design and architecture.

**Documentation**: For detailed usage instructions and examples, refer to the official tikz-uml manual: https://perso.ensta-paris.fr/~kielbasi/tikzuml/var/files/doc/tikzumlmanual.pdf

## Template Structure

```
├── main.tex              # Main document file
├── config/               # Configuration files
│   ├── packages.tex      # Package imports and configurations
│   ├── layout.tex        # Page layout and formatting settings
│   └── style.tex         # Custom styling and commands
├── frontmatter/          # Front matter sections
│   ├── titlepage.tex     # Title page
│   ├── dedication.tex    # Dedication page
│   ├── acknowledgements.tex # Acknowledgements
│   ├── résumé.tex        # French abstract/summary
│   ├── abstract.tex      # English abstract
│   ├── abbreviations-acronyms.tex # List of abbreviations
│   └── general-introduction.tex # General introduction
├── chapters/             # Main content chapters
│   ├── company-presentation.tex # Company/organization presentation
│   ├── project-management.tex   # Project management methodology
│   ├── state-of-the-art.tex     # Literature review/state of art
│   ├── modeling.tex      # System modeling and design
│   └── demo.tex          # Implementation and demonstration
├── backmatter/           # Back matter sections
│   ├── conclusion.tex    # General conclusion
│   └── appendices.tex    # Appendices
├── assets/              # Images
├── References.bib        # Bibliography file
├── tikz-uml.sty         # UML diagram package
└── README.md            # This file
```

## Compilation Notes

- **pdfLaTeX Required**: This template must be compiled with pdfLaTeX to ensure proper rendering of all elements, especially UML diagrams
- **Overleaf Compatibility**: Overleaf automatically uses pdfLaTeX, making it the easiest platform for most users
- **Multiple Compilation**: Run pdfLaTeX multiple times to resolve all cross-references and generate the bibliography correctly

## Customization

- Modify the title page information in `frontmatter/titlepage.tex`
- Update configuration files in the `config/` directory:
  - `packages.tex` - Add or remove LaTeX packages
  - `layout.tex` - Adjust page margins, spacing, and layout settings
  - `style.tex` - Customize fonts, colors, and styling commands
- Edit frontmatter sections in the `frontmatter/` directory as needed
- Add your content to the chapter files in the `chapters/` directory
- Include assets in the `assets/` directory
- Update `References.bib` with your bibliography entries
- Modify backmatter sections in the `backmatter/` directory

## Contributing

Feel free to submit issues or pull requests to improve this template. Contributions for additional features or bug fixes are welcome.

## License

This template is provided as-is for academic use. Please check individual package licenses for specific usage terms.
