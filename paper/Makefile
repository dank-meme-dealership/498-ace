TEX = paper.tex

PDF = paper.pdf

all: $(PDF)

%.pdf: $(TEX)
	pdflatex $*

clean:
	$(RM) *.aux *.log $(PDF)
