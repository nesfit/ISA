all: cv4.pdf

cv4.dvi: cv4.tex theory.tex lab4-zadani.tex Makefile local.bib  ../rfc.bib
	latex $<
	bibtex cv4
	latex $<
	latex $<

%.ps: %.dvi
	dvips -f -t a4 $< > $@

%.pdf: %.ps
	ps2pdf14 -sPAPERSIZE=letter $<

clean:
	rm *.aux *.dvi *.log *.blg *.bbl
