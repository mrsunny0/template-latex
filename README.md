# Latex Template

One Paragraph of project description goes here

<!-- ----------------------------------------------------------------------- -->
<!-- Running templates -->
<!-- ----------------------------------------------------------------------- -->
## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software and how to install them

```
Give examples
```

### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo


<!-- ----------------------------------------------------------------------- -->
<!-- Running templates -->
<!-- ----------------------------------------------------------------------- -->
## Compiling

On Atom, change from xelatex to pdflatex

- `Atom > Preferences > Packages > latex > Settings`

On Texmaker

- `Quickbuild`


<!-- ----------------------------------------------------------------------- -->
<!-- Coding style and formatting -->
<!-- ----------------------------------------------------------------------- -->
## Coding style and formatting

### Graphic paths
```latex
\graphicspath{%
  {path1},
  {path2},
}
```

### Include paths
```latex
\makeatletter
  \def\input@path{%
    {path1},
    {path2},
  }
\makeatother
```


### Figures
Figure subpanels should be labelled as (`\textbf{a,b,c}`).

```latex
\begin{figure}[H]
  \centering
	\includegraphics[width=\linewidth]{global-waste-map.png}
	\caption[main caption]
	{
    \textbf{main caption}\protect\footnotemark.
    ... more caption
  }
	\label{figure:chapter1:global-waste-map}
\end{figure}
\footnotetext{
  data available at: \url{https://datacatalog.worldbank.org/dataset/what-waste-global-database}
}
```

### Tables
Information on p b m alignment: https://tex.stackexchange.com/questions/35293/p-m-and-b-columns-in-tables

![](https://i.stack.imgur.com/NHPLq.png)

Create your own column types

```latex
\newcolumntype{P}[1]{>{\centering\arraybackslash}p{#1}}
\newcolumntype{M}[1]{>{\centering\arraybackslash}m{#1}}
\newcolumntype{L}[1]{>{\arraybackslash}p{#1}}
\newcolumntype{Q}[1]{>{\arraybackslash}m{#1}}
\newcolumntype{B}[1]{>{\arraybackslash}b{#1}}
```

```latex
\begin{table}[H]
  \centering
	\small
	\input{external-table-doc.tex}
	\caption[main caption]
	{
		\textbf{main caption}
		... more caption
  }
	\label{figure:chapter1:global-waste-map}
\end{table}
```

### Cross-reference and labeling
Package `href` has some bugs when working with the `xr` package. Using `xr-hyper` before implementing the `href` package also introduces some bugs that were hard to identify. Instead, use the `zref` package.

In `refextdoc.sty`
```latex
% if not using hyperref
\usepackage{xr}
\usepackage{xr-hyper}
\externaldocument[ext-]{path_to_references} % do not need end /

% if using hyperref
\usepackage{nameref,zref-xr}
\zxrsetup{toltxlabel}
\zexternaldocument*[ext-]{path_to_references} % do not need end /
```

```latex
\label{type:chapter:detail}
```

### Footnotes
Figures should be followed by footnotemark (before the period). Footnotetext should follow figure enviornment to add data availability

```latex
	some sentence that needs a footnote\footnote{}.

	some sentence in an environment that needs a footnote\protect\footnotemark
	...
	\footnotetext{}
```

### Bib and Biblatex(+biber)
- [Overleaf instructiosn](https://www.overleaf.com/learn/latex/bibliography_management_with_biblatex)
- [Discussion on StackExchange](https://tex.stackexchange.com/questions/41821/creating-bib-file-containing-only-the-cited-references-of-a-bigger-bib-file)

In the preamble
```latex
\usepackage[citestyle=numeric,
	backend=biber,
	style=numeric-comp,  % cite instances such as 1-5
	sorting=none,
	refsection=chapter,
	doi=false,           % supress digital object identifier
	isbn=false,          % supress international standard book number
	url=false            % suppress url and date of access
	]{biblatex}

% add bibliography paths
\addbibresource{/path/to/.bib}
\addbibresource{/path/to/another/.bib}
```

In document
```latex
\begin{document}

% ...
\printbibliography

\end{document}
```

### Annotations
```latex
%---------------------------------------------------------------------------%
%                                   BREAK                                   %
%---------------------------------------------------------------------------%
```

```latex
%***************************************************************************%
%                                 CHAPTER X                                 %
%***************************************************************************%
```

```latex
%===========================================================================%
% SECTION
%===========================================================================%
```

```latex
%-----------------------------------------------------------------%
% SUBSECTION
%-----------------------------------------------------------------%
```

```latex
%.......................................................%
% SUBSUBSECTION
%.......................................................%
```

```latex
%===============%
% FIGURES
%===============%
```

```latex
%~~~~~~~~~~~~~~~%
% TABLES
%~~~~~~~~~~~~~~~%
```

```latex
%:::::::::::::::%
% EQUATIONS
%:::::::::::::::%
```

```latex
%...............%
% INPUT
%...............%
```

```latex
%---------------%
% SPECIFIC NOTE
%---------------%
```

```latex
%===============================BIBLIOGRAPHY================================%
```

```latex
% all comments should be lower cased, unless denoting a particular section (e.g. Chapter inputs)
```

```latex
% comment
```

```latex
%% comment heading
```

```latex
%/ block comment
%| ...
%| ...
%| ...
%\ block comment
```

<!-- ----------------------------------------------------------------------- -->
<!-- Built with -->
<!-- ----------------------------------------------------------------------- -->
## Built With

* Texmaker
* Atom
* Atom latex plugin
* MikeTex
* Biber

<!-- ----------------------------------------------------------------------- -->
<!-- Contributing -->
<!-- ----------------------------------------------------------------------- -->
## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

<!-- ----------------------------------------------------------------------- -->
<!-- Versioning -->
<!-- ----------------------------------------------------------------------- -->
## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags).

<!-- ----------------------------------------------------------------------- -->
<!-- Authors -->
<!-- ----------------------------------------------------------------------- -->
## Authors

* **George Sun** - *Initial work* - [mrsunny0](https://github.com/mrsunny0)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

<!-- ----------------------------------------------------------------------- -->
<!-- License -->
<!-- ----------------------------------------------------------------------- -->
## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

<!-- ----------------------------------------------------------------------- -->
<!-- Acknowledgments -->
<!-- ----------------------------------------------------------------------- -->
## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc
