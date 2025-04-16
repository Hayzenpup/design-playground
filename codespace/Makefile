.PHONY: all clean

PUMLS := $(wildcard *.puml)
SVGS := $(PUMLS:%.puml=out/%.svg)
PDFS := $(PUMLS:%.puml=out/%.pdf)
PLANTUML := $(java -jar $HOME/.local/plantuml.jar)
all: $(SVGS) $(PDFS)

out/%.svg : %.puml | out
	java -jar $(HOME)/.local/plantuml.jar -tsvg -o out $<

out/%.pdf: out/%.svg
	inkscape $< --export-type=pdf --export-filename=$@

out:
	mkdir -p out

clean:
	rm -rf out

