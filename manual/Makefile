TEX=latex
BIB=bibtex
NAME=manual

BIBLIO = $(shell ls *.bib) \
			../rfc.bib

TEX_FILES = $(shell ls *.tex) \
			$(BIBLIO)

all: $(NAME).pdf

$(NAME).dvi: $(TEX_FILES) Makefile
	$(TEX) $(NAME)
	$(BIB) $(NAME)
	$(TEX) $(NAME)
	$(TEX) $(NAME)

%.ps: %.dvi
	dvips -f -t a4 $< > $@

%.pdf: %.ps
	ps2pdf14 -sPAPERSIZE=letter $<

clean:
	rm *.aux *.dvi *.log *.blg *.bbl
