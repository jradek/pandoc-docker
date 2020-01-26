pandoc-eqnos:
	git clone https://github.com/tomduck/pandoc-eqnos

pandoc-fignos:
	git clone https://github.com/tomduck/pandoc-fignos

pandoc-secnos:
	git clone https://github.com/tomduck/pandoc-secnos

pandoc-tablenos:
	git clone https://github.com/tomduck/pandoc-tablenos

.PHONY: tomhuck
tomhuck: pandoc-eqnos pandoc-fignos pandoc-secnos pandoc-tablenos

.PHONY: run-pandoc-xnos-demos
run-pandoc-xnos-demos: tomhuck
	docker run --rm -v "`pwd`:/data" jradek/pandoc-latex-with-filters:2.9.1.1 ./run-pandoc-xnos-demos.sh

###############################################################################

pandoc-crossref:
	git clone https://github.com/lierdakil/pandoc-crossref.git

.PHONY: lierdakil
lierdakil: pandoc-crossref

.PHONY: run-crossref-demo
run-crossref-demo: lierdakil
	docker run --rm -v "`pwd`:/data" jradek/pandoc-latex-with-filters:2.9.1.1 ./run-crossref-demo.sh

###############################################################################

.DEFAULT_GOAL := all
.PHONY: all
all: run-pandoc-xnos-demos run-crossref-demo

.PHONY: clean
clean:
	rm -rf pandoc-crossref
	rm -rf pandoc-*nos
