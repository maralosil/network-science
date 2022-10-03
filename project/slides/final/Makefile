DOC := final
TEX := $(addsuffix .tex,$(DOC))
PDF := $(addsuffix .pdf,$(DOC))
PS  := $(addsuffix .ps,$(DOC))
DVI := $(addsuffix .dvi,$(DOC))

.PHONY: all clean

all: $(PDF)

$(PDF): $(PS)
	ps2pdf $<

$(PS): $(DVI)
	dvips -o $@ $<

$(DVI): $(TEX)
	for i in $$(seq 2);		\
	do				\
		latex $<;		\
		if [ $$? -ne 0 ];	\
		then			\
			break;		\
		fi;		\
	done;

clean:
	@rm -f *.aux *.log *.toc *.nav *.snm *.out *.dvi *.ps *.pdf
