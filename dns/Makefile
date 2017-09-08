all: cv3.pdf

cv3.dvi: cv3.tex theory.tex lab3-zadani.tex Makefile local.bib  ../rfc.bib
	latex $<
	bibtex cv3
	latex $<
	latex $<

%.ps: %.dvi
	dvips -f -t a4 $< > $@

%.pdf: %.ps
	ps2pdf14 -sPAPERSIZE=letter $<

clean:
	rm *.aux *.dvi *.log *.blg *.bbl
