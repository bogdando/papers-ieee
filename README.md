# papers-ieee
LaTeX Templates and drafts of misc papers for IEEE

See also:

* [LaTeX templates instructions](http://www.ctan.org/tex-archive/macros/latex/contrib/IEEEtran/IEEEtran_HOWTO.pdf)
* [Template source](https://www.ieee.org/content/dam/ieee-org/ieee/web/org/conferences/Conference-LaTeX-template_7-9-18.zip) -
  it is also stored in `./examples`.

# in the current development (looking for co-authors!)

A position paper for [ICFC 2019](http://conferences.computer.org/ICFC/2019/),
IEEE International Conference on Cloud Engineering, 2019.

Please contribute for [draft contents](./ICFC-2019/contents.md), deadline is
Nov 8, 2018 (but may be extended hopefully). To add you as an author, please
let me know (mailto:bdobreli@redhat.com, #bogdando at freenode IRC) your EDAS ID.
To register, visit [EDAS info page](https://edas.info).

# build steps

Debian OS family:

```
# apt install texlive-science texlive-latex-base gv
# pdflatex foo.tex
```

Via container:

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

# live update for compiled pdf

Use ``gv -watch foo.pdf``.

# build a ps file to convert it into PDF online

```
# docker run --rm -it -v $(pwd):/home bogdando/texlive latexmk -ps foo.tex
```
Then convert the resulting PS file to a PDF with an online converter, like [this one](https://www.ps2pdf.com/convert-ps-to-pdf).
Note, not an each converter works well for EDAS system...
