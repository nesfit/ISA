TEX=latex
BIB=bibtex
PDF=cv5

all: $(PDF).pdf

$(PDF).dvi: $(PDF).tex theory.tex lab5-zadani.tex Makefile local.bib  ../rfc.bib
	$(TEX) $<
	$(BIB) $(PDF)
	$(TEX) $<
	$(TEX) $<

%.ps: %.dvi
	dvips -f -t a4 $< > $@

%.pdf: %.ps
	ps2pdf14 -sPAPERSIZE=letter $<

clean:
	rm *.aux *.dvi *.log *.blg *.bbl
