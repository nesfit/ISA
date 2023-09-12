all: cv1.pdf

manual:
	$(MAKE) -C ../manual

cv1.dvi: cv1.tex lab1-zadani.tex Makefile manual
	latex $<
	latex $<

%.ps: %.dvi
	dvips -f -t a4 $< > $@

%.pdf: %.ps
	ps2pdf14 -sPAPERSIZE=letter $<

clean:
	rm *.aux *.dvi *.log *.blg *.bbl
