# Frugal AI Report

This repository contains the LaTeX source for the ACL-style report for the Frugal AI course. The project uses the official ACL formatting files and is designed to compile into a PDF paper.

> Attribution: this repository adapts the ACL conference LaTeX template from the official ACL style resources available on [Overleaf](https://www.overleaf.com/latex/templates/association-for-computational-linguistics-acl-conference/jvxskxpnznfj) and the [GitHub repository](https://github.com/acl-org/acl-style-files). We acknowledge the original ACL template authors and maintainers for the formatting and bibliography conventions used here.

## 1. What this project is

The main goal is to write and compile a conference-style paper using LaTeX. The repository includes the paper source, the ACL style files, and a bibliography file where references are stored.

## 2. Quick start

### Option A: Local compilation with VS Code (recommended)

1. Install a LaTeX distribution:
   - Windows: [MiKTeX](https://miktex.org/download) or [TeX Live](https://www.tug.org/texlive/)
   - macOS: [MacTeX](https://www.tug.org/mactex/)
   - Linux: `sudo apt install texlive-full`

2. Install the LaTeX Workshop extension in VS Code.

3. Open this folder in VS Code.

4. Compile the paper:
   - Open `acl_latex.tex`
   - Click the “Build LaTeX project” button in the LaTeX Workshop panel
   - The generated PDF will appear in the project root

### Option B: Overleaf

1. Create a new project in Overleaf.
2. Upload the files from this repository, or sync the GitHub repository directly.
3. The PDF will be generated automatically by Overleaf.

## 3. Directory and file explanations

Below is a brief explanation of each file in this directory:

- `acl_latex.tex`: the main LaTeX source file for the paper. This is the file you will edit most of the time when writing sections, figures, and references.
- `acl_lualatex.tex`: a variant of the template for LuaLaTeX users. It is useful if you need better Unicode support or specific engine compatibility.
- `acl.sty`: the main ACL formatting style file. This controls the layout, fonts, spacing, and overall conference formatting.
- `acl_natbib.bst`: the bibliography style file used by BibTeX to format references in the bibliography.
- `custom.bib`: the file where you should add your project’s bibliography entries. This is the dedicated file for citations that are not already in the ACL Anthology.
- `anthology.bib.txt`: a local copy of the ACL Anthology bibliography data. It is optional for many papers, but useful as a reference source for existing ACL papers.
- `formatting.md`: the formatting guide from ACL. It explains how to follow conference rules, including page limits, sections, and formatting expectations.
- `README.md`: this file. It explains the project structure and how to compile and manage the bibliography.
- `tests/regression/run_tests.py`: a simple regression check script used to validate the project state or basic repository checks.

## 4. How to write the paper

The main paper source is in `acl_latex.tex`. This file includes:

- the document class and style setup
- title and author information
- the abstract
- section structure
- bibliography commands
- appendix sections

When writing the paper, edit `acl_latex.tex` rather than the style files unless you are intentionally changing formatting settings.

## 5. How to create the bibliography

The bibliography is managed with BibTeX entries stored in `custom.bib`.

### Recommended workflow

1. Find a paper on Google Scholar.
2. Click the “Cite” button.
3. Choose the “BibTeX” option.
4. Copy the generated BibTeX entry.
5. Open `custom.bib`.
6. Paste the entry at the end of the file.
7. Keep one entry per reference.
8. Add a citation in the LaTeX document using the entry key.

### Example

Suppose Google Scholar gives you a BibTeX entry like this:

```bibtex
@inproceedings{smith2024fairness,
  title={Fairness in Machine Learning},
  author={Smith, John and Doe, Jane},
  booktitle={Proceedings of the Conference},
  year={2024},
  pages={1--10}
}
```

Then paste it into `custom.bib`:

```bibtex
@inproceedings{smith2024fairness,
  title={Fairness in Machine Learning},
  author={Smith, John and Doe, Jane},
  booktitle={Proceedings of the Conference},
  year={2024},
  pages={1--10}
}
```

Then in the paper, cite it like this:

```latex
\citep{smith2024fairness}
```

or

```latex
\citet{smith2024fairness}
```

The bibliography is included in the LaTeX file with:

```latex
\bibliography{custom}
```

This command is already present in `acl_latex.tex`.

### Important notes

- Use `custom.bib` for your own references.
- Do not paste random unformatted text into the bibliography file.
- Keep the BibTeX syntax valid: each entry must have a unique key such as `smith2024fairness`.
- If a paper is already in the ACL Anthology, you may also consult `anthology.bib.txt`, but the usual workflow is to keep your project references in `custom.bib`.

## 6. Working with Git and collaboration

When you make changes:

```bash
git checkout -b your-branch-name
git add .
git commit -m "Describe your changes"
git push origin your-branch-name
```

Then open a pull request on GitHub for review.

## 7. Troubleshooting

If the PDF does not compile:

- Make sure the LaTeX distribution is installed
- Rebuild the project in VS Code
- Check for missing braces or invalid BibTeX entries in `custom.bib`
- Ensure you are compiling the correct file: `acl_latex.tex`

## 8. Final recommendation

For this project, the simplest workflow is:

1. Write sections in `acl_latex.tex`
2. Add references to `custom.bib`
3. Cite them in the text with `\citep{...}` or `\citet{...}`
4. Compile the document until the PDF is correct

This keeps the paper clean and consistent with the ACL template.
