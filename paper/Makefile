.PHONY: all clean

all: paper.pdf

paper.pdf: paper.md paper.bib
	pandoc paper.md \
		--bibliography=paper.bib \
		--citeproc \
		--metadata author="Yash Munnalal Gupta" \
		--metadata date="2025-09-30" \
		--metadata subject="DNA electron counting, computational biology" \
		-o paper.pdf \
		--pdf-engine=pdflatex

clean:
	rm -f paper.pdf
