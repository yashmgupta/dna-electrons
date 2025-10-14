# Paper Generation

This directory contains the academic paper for the `dna-electrons` package.

## Files

- `paper.md` - Main paper content in Markdown format with YAML metadata
- `paper.bib` - Bibliography in BibTeX format
- `paper.pdf` - Generated PDF output

## Generating the PDF

To regenerate the PDF from the Markdown source, you need:

1. **pandoc** (version 2.x or higher)
2. **LaTeX** (pdflatex)
3. **pandoc-citeproc** or pandoc with built-in citeproc support (pandoc 2.11+)

### Installation

On Ubuntu/Debian:
```bash
sudo apt-get install pandoc texlive-latex-base texlive-latex-extra texlive-fonts-recommended
```

On macOS with Homebrew:
```bash
brew install pandoc
brew install --cask mactex
```

### Build Command

```bash
cd paper
pandoc paper.md \
  --bibliography=paper.bib \
  --citeproc \
  --metadata author="Yash Munnalal Gupta" \
  --metadata date="2025-09-30" \
  --metadata subject="DNA electron counting, computational biology" \
  -o paper.pdf \
  --pdf-engine=pdflatex
```

This command will:
- Process the Markdown content from `paper.md`
- Include citations from `paper.bib` using citeproc
- Set proper PDF metadata (title, author, keywords, etc.)
- Generate `paper.pdf` using pdflatex

## Metadata

The PDF includes the following metadata:
- **Title**: Extracted from YAML front matter
- **Author**: Yash Munnalal Gupta
- **Keywords**: DNA, Python, electron density, bioinformatics, computational biology, molecular modeling, quantum chemistry, FASTA
- **Subject**: DNA electron counting, computational biology
- **Date**: 2025-09-30

## Citations

All citations in the paper are managed through BibTeX. Add new references to `paper.bib` and cite them in `paper.md` using `[@citationkey]` syntax.
