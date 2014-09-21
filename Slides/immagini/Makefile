SVGS=$(wildcard *.svg)
DIAS=$(wildcard *.dia)

.PHONY: all clean eps pdf

all: pdf

pdf: $(SVGS:svg=pdf) $(DIAS:dia=pdf)

#eps: $(SVGS:svg=eps) $(DIAS:dia=eps)

%.eps: %.dia
	dia --nosplash -e $@ $<

#%.eps: %.svg
	inkscape -f $< -E $@

#%.pdf: %.eps
#	epstopdf $<

%.pdf: %.svg
	inkscape -f $< -A $@

clean:
	rm $(SVGS:svg=eps) $(SVGS:svg=pdf) $(DIAS:dia=eps) $(DIAS:dia=pdf) 2>/dev/null; true
