.PHONY: all distclean clean

all: neural_network.png artificial_neuron.png

neural_network.png: neural_network.dot
	dot -o $@ -T png $<

artificial_neuron.png: artificial_neuron.tex.dot
	pipenv run dot2tex --figpreamble "\LARGE" --crop --margin "0.1in" $< > $(<:%.tex.dot=%.tex)
	lualatex $(<:%.tex.dot=%.tex)
	pdftoppm -r 72 -png -singlefile $(<:%.tex.dot=%.pdf) $(@:%.png=%)

distclean: clean
	rm *.png 2>/dev/null || true

clean:
	rm *.aux *.log *.pdf *.tex 2>/dev/null || true
