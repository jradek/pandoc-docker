# Readme

Enhanced pandoc latex docker image with useful filters installed.

The image is [jradek/pandoc-latex-with-filters](https://hub.docker.com/r/jradek/pandoc-latex-with-filters)

## Available filters

| Filter | Description | Programming Language |
|:---|:---|:---|
| [pandoc-crossref](https://github.com/lierdakil/pandoc-crossref) | Pandoc filter for numbering figures, equations, tables and cross-references to them | Haskell |
| [pandoc-eqnos](https://github.com/tomduck/pandoc-eqnos) | A pandoc filter for numbering equations and equation references. | Python |
| [pandoc-fignos](https://github.com/tomduck/pandoc-fignos) | A pandoc filter for numbering figures and figure references. | Python |
| [pandoc-secnos](https://github.com/tomduck/pandoc-secnos) | A pandoc filter for numbering section references. | Python |
| [pandoc-tablenos](https://github.com/tomduck/pandoc-tablenos) | A pandoc filter for numbering tables and table references. | Python

## For contributors: Upgrading the image

1. Go to [https://github.com/lierdakil/pandoc-crossref/releases]() to figure out the latest *crossref_release* (e.g. *v0.3.6.3*) and **the matching** *pandoc_version* (e.g. *2.9.2.1*)
2. Update [Makefile]() variables **PANDOC_VERSION** and
**CROSSREF_RELEASE** accordingly
3. Build the image `make all`. On success, the image *jradek/pandoc-latex-with-filters:$(pandoc_release)* is created
4. Manually (sad but true, need to automate this) update this image in [test/Makefile](), e.g. *jradek/pandoc-latex-with-filters:2.9.2.1*
5. Run tests: `cd test && make all`
