GREGORIO=gregorio
LATEX=lualatex --shell-escape

MAINTEX=MissaI
GABC=$(shell find . -name '*.gabc')
SCORES=$(patsubst %.gabc,%,$(GABC))
TEXSCORES=$(patsubst %.gabc,%.tex,$(GABC))


all: $(TEXSCORES) $(MAINTEX).pdf clean-aux

%.pdf:
	$(LATEX) $(patsubst %.pdf,%.tex,$@)

%.tex:
	$(GREGORIO) $(patsubst %.tex,%.gabc,$@)

clean: clean-aux clean-pdf

clean-pdf:
	rm -f *.pdf

clean-aux:
	rm -f $(TEXSCORES) *.aux *.gtex *.log *.gaux

help:
	@echo
	@echo PDF Build:
	@echo
	@echo "  all            Build PDF output from source files in GABC format"
	@echo
	@echo "  clean          Delete all files produced"
	@echo
	@echo "  clean-aux      Delete all files produced except PDF output"
	@echo
