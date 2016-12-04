TEX = paper.tex

CLS = acmsmall.cls

STY = acmcopyright.sty

PACKAGE = ogden-royster

PDF = ${TEX:%.tex=%.pdf}

PWD= ${shell pwd}

all: $(PDF)

%.pdf: %.tex $(CLS) $(STY) .FORCE
	pdflatex $*
	bibtex $*
	pdflatex $*
	while ( grep -q '^LaTeX Warning: Label(s) may have changed' $*.log)\
	do pdflatex $*; done

clean:
	$(RM) $(PDF) *.aux *.log  *.blg *.bbl

zip: all clean
	zip $(PACKAGE).zip * -x '*~' -x '*.tgz' -x '*.zip' -x CVS -x 'CVS/*'

.FORCE:
