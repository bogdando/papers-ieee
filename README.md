# papers-ieee
LaTeX Templates and drafts of misc papers for IEEE

See also:

* [LaTeX templates instructions](http://www.ctan.org/tex-archive/macros/latex/contrib/IEEEtran/IEEEtran_HOWTO.pdf)
* [Template source](https://www.ieee.org/content/dam/ieee-org/ieee/web/org/conferences/Conference-LaTeX-template_7-9-18.zip) -
  it is also stored in `./examples`.

# In development (looking for co-authors!)

* DRAFT: [Multi-Cloud Edge Computing Challenges (Short Positioning Document)](./ICFC-2019/LaTeX/position_paper_1570506394.tex)

To become a co-author, please contribute for the following topics:

* Clarify why geo-replicated causal consistent data stores match the fog
  computing environments.
* Bring a concrete NF application example to motivate key challenges and
  articulate why geo-replicated causal consistent data stores are the solution
  that should also become a unified Replication-as-a-Service solution.
* Aside of data stores, elaborate on: resource management (Day 1 and Day 2
  operations), high availability, extensibility, and robustness.
* Bring another example of a distributed app (using micro-services) to fit those
  uncovered areas. It should also illustrate the orthogonal to data stores
  approach, wihch is relying on causality among API-to-API communications being
  propagated through an example replication topology).
* Make it human readable :-)

**Thank you all who has provided such valuable feedback via blind reviews!**

# TeX build steps

Debian OS family:

```
# apt install texlive-science texlive-latex-base gv
# pdflatex foo.tex
```

## Build via a container

```
# docker run --rm -it -v $(pwd):/home danteev/texlive:TL2017 \
    texliveonfly -c latexmk -a "-pdf -f -synctex=0" foo.tex
```

Beware, it gets quite a fat image of a 6G, it may be faster for you to build it
locally by hand:
```
# git clone https://github.com/dante-ev/docker-texlive
# cd docker-texlive
# docker build .
```

## Live update for compiled pdf

Use ``gv -watch foo.pdf``.

## Build a ps file to convert it into PDF online

```
# docker run --rm -it -v $(pwd):/home bogdando/texlive latexmk -ps foo.tex
```
Then convert the resulting PS file to a PDF with an online converter, like [this one](https://www.ps2pdf.com/convert-ps-to-pdf).
Note, not an each converter works well for EDAS system...
