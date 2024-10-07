TEX=pdflatex
BIB=bibtex
PDF=cv5

all: $(PDF).pdf

$(PDF).pdf: $(PDF).tex lab5-zadani.tex Makefile
	$(TEX) $<
	$(TEX) $<

clean:
	rm *.aux *.dvi *.log *.blg *.bbl *.pdf
