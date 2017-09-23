all: cv1.pdf

cv1.dvi: cv1.tex theory.tex lab1-zadani.tex Makefile local.bib
	latex $<
#	bibtex cv1
	latex $<
	latex $<

%.ps: %.dvi
	dvips -f -t a4 $< > $@

%.pdf: %.ps
	ps2pdf14 -sPAPERSIZE=letter $<

clean:
	rm *.aux *.dvi *.log *.blg *.bbl
