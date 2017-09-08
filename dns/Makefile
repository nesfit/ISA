all: lab3-zadani.pdf cv3.pdf

cv3.dvi: cv3.tex Makefile local.bib  ../rfc.bib
	latex $<
	bibtex cv3
	latex $<
	latex $<

lab3-zadani.dvi: lab3-zadani.tex Makefile local.bib  ../rfc.bib
	latex $<
	latex $<

%.ps: %.dvi
	dvips -f -t a4 $< > $@

%.pdf: %.ps
	ps2pdf14 -sPAPERSIZE=letter $<

clean:
	rm *.aux *.dvi *.log *.blg *.bbl
