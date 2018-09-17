TEX=latex
BIB=bibtex
PDF=cv5

all: $(PDF).pdf

$(PDF).dvi: $(PDF).tex lab5-zadani.tex Makefile
	$(TEX) $<
	$(TEX) $<

%.ps: %.dvi
	dvips -f -t a4 $< > $@

%.pdf: %.ps
	ps2pdf14 -sPAPERSIZE=letter $<

clean:
	rm *.aux *.dvi *.log *.blg *.bbl
