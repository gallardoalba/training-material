MINDMAPS := $(wildcard *.mindmap.yml)
INPUTS := $(wildcard *.plantuml.txt)
OUTPUTS := $(INPUTS:.txt=.svg)

all: plantuml.jar $(MINDMAPS) $(OUTPUTS)

$(OUTPUTS): $(INPUTS) $(MINDMAPS)
	python mindmap_yaml_to_plantuml.py $(MINDMAPS)
	java -jar plantuml.jar -c plantuml_options.txt -tsvg $(INPUTS)

plantuml.jar:
	wget http://jaist.dl.sourceforge.net/project/plantuml/plantuml.jar
