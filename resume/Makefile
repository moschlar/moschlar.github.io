PANDOC?=pandoc
PANDOC_OPTS=-s
PANDOC_HTML_OPTS=
PANDOC_PDF_OPTS=-V documentclass=scrartcl

.PHONY: all clean

all: $(patsubst %.md,%.html,$(wildcard *.md)) $(patsubst %.md,%.pdf,$(wildcard *.md))

%.html: %.md resumeB.html resumeA.html
	$(PANDOC) $(PANDOC_OPTS) $(PANDOC_HTML_OPTS) -c ../style.css -B resumeB.html -A resumeA.html -o $@ $<

%.pdf: %.md %.H.tex
	$(PANDOC) $(PANDOC_OPTS) $(PANDOC_PDF_OPTS) -H $*.H.tex -o $@ $<

clean:
	rm -f *~ *.html *.log *.pdf
