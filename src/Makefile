.POSIX:

SHELL = /bin/sh

.SUFFIXES:
.SUFFIXES: .pdf .tex

SRC = wizzard.tex
PDF = $(SRC:tex=pdf)

LATEX = pdflatex
LATEX_OPTS = -halt-on-error

APP = Preview

all: $(PDF)

.tex.pdf:
	$(LATEX) $(LATEX_OPTS) $*
	$(LATEX) $(LATEX_OPTS) $*

interactive:
	@while read -r -p 'compile>'; do $(MAKE) preview; done

preview: $(PDF)
	open -a $(APP) $(PDF)

clean:
	git clean -fdx -e '*.sw*' -e '*.vim'
