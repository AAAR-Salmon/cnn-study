.PHONY: all clean

all: neural_network.png artificial_neuron.png

neural_network.png: neural_network.dot
	dot -o $@ -T png $<

artificial_neuron.png: artificial_neuron.tex.dot
	pipenv run dot2tex $< > $(<:%.tex.dot=%.tex)
	lualatex $(<:%.tex.dot=%.tex)
	pdftoppm -png -singlefile $(<:%.tex.dot=%.pdf) $(@:%.png=%)

clean:
	@rm *.aux *.log *.pdf *.png *.tex
