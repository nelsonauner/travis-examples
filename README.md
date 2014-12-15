Example: knitr-example
==========================
[![Build Status](https://travis-ci.org/nelsonauner/travis-examples.png?branch=knitr)](https://travis-ci.org/nelsonauner)


This branch illustrates how to compile a knitr document under travis. Key points:

 * `DESCRIPTION` file. This should contain all R packages (including `knitr`) needed to compile your document.
 * `.travis.yml` file. In particular, note

```yml
script: 
    - Rscript -e "require(knitr); fname = 'example.Snw'; knit(fname); purl(fname)"
    - pdflatex example
```
and

```yml
env:
  global:
    - BOOTSTRAP_LATEX="1"    
```

