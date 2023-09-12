all: cv1.pdf

manual:
	$(MAKE) -C ../manual

cv1.pdf: cv1.tex lab1-zadani.tex Makefile
	pdflatex $<
	pdflatex $<

clean:
	rm *.aux *.dvi *.log *.blg *.bbl
