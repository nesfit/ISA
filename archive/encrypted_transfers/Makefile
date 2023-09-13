TEX=latex
BIB=bibtex
PDF=encrypted_transfers

all: $(PDF).pdf arch

$(PDF).dvi: $(PDF).tex Makefile
	$(TEX) $<
	$(TEX) $<

%.ps: %.dvi
	dvips -f -t a4 $< > $@

%.pdf: %.ps
	ps2pdf14 -sPAPERSIZE=letter $<

clean:
	rm -f *.aux *.dvi *.log *.blg *.bbl *.ps

arch: lab2-arch.tex
	latex lab2-arch.tex
	dvips -f -t a4 lab2-arch.dvi > lab2-arch.ps
	ps2pdf14 -sPAPERSIZE=letter lab2-arch.ps
