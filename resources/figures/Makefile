.PHONY: all clean

all: neural-network.png artificial-neuron.png

neural-network.png: neural-network.dot
	dot -o $@ -T png $<

artificial-neuron.png: artificial-neuron.tex.dot
	pipenv run dot2tex $< > $(<:%.tex.dot=%.tex)
	lualatex $(<:%.tex.dot=%.tex)
	pdftoppm -png -singlefile $(<:%.tex.dot=%.pdf) $(@:%.png=%)

clean:
	@rm *.aux *.log *.pdf *.png *.tex
