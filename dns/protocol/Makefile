all: cv3.pdf

cv3.dvi: cv3.tex lab3-protocol.tex Makefile
	latex $<
	latex $<
	latex $<

%.ps: %.dvi
	dvips -f -t a5 $< > $@

%.pdf: %.ps
	ps2pdf14 -sPAPERSIZE=a5 $<

clean:
	rm *.aux *.dvi *.log *.blg
