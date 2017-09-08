LATEX=cslatex
#LATEX=latex
BIBTEX=bibtex
DVIPS=dvips
PS2PDF=ps2pdf13
PSNUP=psnup 
CC=gcc
CFLAGS=-Wall
LATEX2HTML=tth -e2
TREX=trex

all: management.pdf

%: %.ps
#%.two: %.ps.2

%.o: %.c
	$(CC) $(CFLAGS) -o $@ $<

# implicit rules

%.dvi: %.tex
	$(LATEX) $<
#	$(BIBTEX) $*
%.ps: %.dvi
	$(DVIPS) $<
%.pdf: %.ps
	$(PS2PDF) $< $@
%.2ps: %.ps
	$(PSNUP) -2 $< > $@
%.4ps: %.ps
	$(PSNUP) -l -4 $< > $@
%.html: %.tex
	$(LATEX2HTML) $< > $@

cleantrex:
	rm -f form_red oc.out *~ fic_implcontrainte_err.txt fic_mincontrainte_err.txt

%.aut:  cleantrex %.if %.cnd
	rm -f $*.tr $*.tr.dot
	$(TREX) -init $*.if -c $*.cnd -cp $(CP) -sg $*.aut  -res $*.res -tr $*.tr -e

# local dependences
$(SOURCE).dvi: $(SOURCE).tex
$(SOURCE).ps: $(SOURCE).dvi
$(SOURCE).pdf: $(SOURCE).ps
$(SOURCE).ps.2: $(SOURCE).ps
$(SOURCE).html: $(SOURCE).tex

# cleaning
clean: 
	rm -f *.dvi *.ps *.ps.2 
cleanall:
	rm -f *~ *.log *.aux *.dvi *.ps.2 *bbl *blg
