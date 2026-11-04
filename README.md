# AAU Front Pages — LaTeX Report Template

**14 ready-to-use cover designs** for Aalborg University (AAU) projects, together with a structured LaTeX `book` document, an AAU title page, mathematics commands, theorem boxes, code listings, and bibliography support.


## Contents

- [Cover gallery — all 14 designs](#cover-gallery--all-14-designs)
- [Quick start](#Quick-start)
- [Repository structure](#repository-structure)
- [Build environments and document layouts](#build-environments-and-document-layouts)
- [Packages, styling, and configuration](#packages-styling-and-configuration)
- [Custom command reference](#custom-command-reference)
- [Theorems and custom environments](#theorems-and-custom-environments)
- [Practical examples](#practical-examples)

## Cover gallery — all 14 designs
To select a cover, include the corresponding file in `master.tex` using `\include{incl/misc/frontpage}`. For numbered designs, use `\include{incl/misc/frontpageN}`, where `N` is the desired design number (1–13).

For example, `\include{incl/misc/frontpage5}` selects Design 06.

Only include one front page at a time. These are cover choices, not different document classes.

### Light, fine-line waves

| Design 02 · Gentle radial flow | Design 03 · Fine upper-left sweep |
|:--:|:--:|
| <img src="assets/front-pages/frontpage1.jpg" width="275" alt="Front page 1: fine, pale curved lines radiating from the centered AAU logo" /> | <img src="assets/front-pages/frontpage2.jpg" width="275" alt="Front page 2: delicate wave lines swelling across the upper-left area" /> |
| [`frontpage1.tex`](incl/misc/frontpage1.tex) · PDF p. 3 | [`frontpage2.tex`](incl/misc/frontpage2.tex) · PDF p. 5 |

| Design 04 · Open flowing lines | Design 05 · Soft horizontal current |
|:--:|:--:|
| <img src="assets/front-pages/frontpage3.jpg" width="275" alt="Front page 3: sparse curved lines leaving a large white space around the title" /> | <img src="assets/front-pages/frontpage4.jpg" width="275" alt="Front page 4: gently drifting narrow waves with a broad white title region" /> |
| [`frontpage3.tex`](incl/misc/frontpage3.tex) · PDF p. 7 | [`frontpage4.tex`](incl/misc/frontpage4.tex) · PDF p. 9 |

### Mid-contrast flowing waves

| Design 06 · S-curved contour | Design 07 · Fanning wave |
|:--:|:--:|
| <img src="assets/front-pages/frontpage5.jpg" width="275" alt="Front page 5: medium-weight flowing lines that curve around the logo and title" /> | <img src="assets/front-pages/frontpage6.jpg" width="275" alt="Front page 6: fanning diagonal and vertical contours" /> |
| [`frontpage5.tex`](incl/misc/frontpage5.tex) · PDF p. 11 | [`frontpage6.tex`](incl/misc/frontpage6.tex) · PDF p. 13 |

| Design 08 · Broad diagonal arcs | Design 09 · Deep curved ribbons |
|:--:|:--:|
| <img src="assets/front-pages/frontpage7.jpg" width="275" alt="Front page 7: prominent curving diagonal blue lines that widen at the bottom" /> | <img src="assets/front-pages/frontpage8.jpg" width="275" alt="Front page 8: broad upper arcs and lower sweeping waves" /> |
| [`frontpage7.tex`](incl/misc/frontpage7.tex) · PDF p. 15 | [`frontpage8.tex`](incl/misc/frontpage8.tex) · PDF p. 17 |

### Bold, high-contrast waves

| Design 01 · Original bold waves | Design 10 · Vertical wave columns |
|:--:|:--:|
| <img src="assets/front-pages/frontpage.jpg" width="275" alt="Original frontpage: closely packed heavy navy curved wave stripes across the cover" /> | <img src="assets/front-pages/frontpage9.jpg" width="275" alt="Front page 9: dark, heavy curving vertical wave bands around the logo" /> |
| [`frontpage.tex`](incl/misc/frontpage.tex) · PDF p. 1 | [`frontpage9.tex`](incl/misc/frontpage9.tex) · PDF p. 19 |

| Design 11 · Dense wide bands | Design 12 · Dark negative-space waves |
|:--:|:--:|
| <img src="assets/front-pages/frontpage10.jpg" width="275" alt="Front page 10: wide, densely packed dark navy wave contours" /> | <img src="assets/front-pages/frontpage11.jpg" width="275" alt="Front page 11: navy-dominant background crossed by white curved stripes" /> |
| [`frontpage10.tex`](incl/misc/frontpage10.tex) · PDF p. 21 | [`frontpage11.tex`](incl/misc/frontpage11.tex) · PDF p. 23 |

| Design 13 · Diagonal dark field | |
|:--:|:--:|
| <img src="assets/front-pages/frontpage12.jpg" width="275" alt="Front page 12: dark blue cover with white diagonal waving bands" /> | |
| [`frontpage12.tex`](incl/misc/frontpage12.tex) · PDF p. 25 | |

### Minimalist design

| Design 14 · Framed typography |
|:--:|
| <img src="assets/front-pages/frontpage13.jpg" width="275" alt="Front page 13: clean white cover with an outlined title panel and a centered AAU logo below" /> |
| [`frontpage13.tex`](incl/misc/frontpage13.tex) · PDF p. 27 |

## Quick start

### 1. Get the project

Use **Code → Download ZIP** on GitHub, or clone the repository:

```bash
git clone https://github.com/MadsMunkNielsen/AAU-front-pages.git
cd AAU-front-pages
```

### 2. Set your project information

Edit the definitions near the top of [`master.tex`](master.tex):

```latex
\def\projecttitle{A Study of Example Problems}
\def\projectsubtitle{Theory and Applications}
\def\projecttheme{Applied Mathematics}
\def\projectdegree{Mathematics-Economics}
\def\projectperiod{Fall Semester 2026}
\def\projectnumber{P1}
\def\projectgroup{X123}
\def\projectauthors{Alice Example\\Bob Example}
\def\projectsupervisors{Dr. Example}
```

### 3. Select exactly one cover

The repository's [`master.tex`](master.tex) is set up as a **showcase**, and therefore currently includes **all 14 covers**, separated by `\cleardoublepage`. For a real report, replace that sequence with one choice, for example:

```latex
\frontmatter
\include{incl/misc/frontpage5} % Change 5 to the number you prefer
\include{incl/misc/titlepage}
\include{incl/misc/contents}
\mainmatter
```

## Repository structure

```text
AAU-front-pages/
├── master.tex                  # Document class, project fields, includes, BibTeX
├── aaumath.sty                 # Collects the three preamble files
├── .latexmkrc                 # Default PDF build via latexmk / pdflatex
├── .gitignore                 # Git exclusions for generated files
├── README.md                  # This guide
├── code/                      # Separate source-code workspace (not a required include)
├── fig/
│   ├── img/
│   │   └── aau/                # PDF wave backgrounds, including Waves.pdf
│   └── tikz/
│       └── aau-badge.tex      # AAU badge used in cover pages
├── incl/
│   ├── pre/
│   │   ├── pkgs.tex           # Imported packages
│   │   ├── cmds.tex           # Shortcuts, theorems, custom environments
│   │   ├── conf.tex           # Color palette, page styling, captions, lists
│   │   └── ext/
│   │       └── aautitlepage.sty # Bundled AAU info-page implementation
│   ├── misc/
│   │   ├── frontpage.tex      # Original cover (PDF page 1)
│   │   ├── frontpage1.tex     # Cover 1 (PDF page 3)
│   │   ├── ...
│   │   ├── frontpage13.tex    # Minimalist cover (PDF page 27)
│   │   ├── titlepage.tex      # Formal AAU info page
│   │   ├── abstract.tex       # Abstract content
│   │   └── contents.tex       # Contents and optional lists
│   ├── main/
│   │   └── Start.tex          # Currently included main-matter file
│   ├── app/                   # Optional appendices
│   └── bib/
│       ├── books.bib
│       ├── articles.bib
│       └── software.bib
└── assets/
    └── front-pages/          # The 14 README JPEG previews
        ├── frontpage.jpg
        ├── frontpage1.jpg
        ├── ...
        └── frontpage13.jpg
```

The `code/` directory can be used to store project-related code.

## Packages, styling, and configuration

[`aaumath.sty`](aaumath.sty) is a small entry point that loads three files in order: [`pkgs.tex`](incl/pre/pkgs.tex), [`cmds.tex`](incl/pre/cmds.tex), and [`conf.tex`](incl/pre/conf.tex).

| Area | Where | Important implementation details |
|---|---|---|
| Mathematical typesetting | `pkgs.tex` | `mathtools`, `amssymb`, `amsthm`, `bbm`, and `bm` |
| Figures and diagrams | `pkgs.tex` | `graphicx`, `tikz`, `subcaption`, `background`, and supporting graphics packages |
| Citations and bibliography | `pkgs.tex` + `master.tex` | `natbib` with `sort, comma`; `apalike` BibTeX style and three `.bib` inputs |
| Algorithms and code | `pkgs.tex` + `cmds.tex` + `conf.tex` | `algorithm`, `algpseudocode`, `listings`; Python listing styles defined in the preamble |
| Official AAU colors | `conf.tex` | `AAUblue1`, `AAUblue2`, `AAUgrey1`–`AAUgrey4`, `AAUgreen`, `AAUteal`, `AAUred` |
| Page geometry and headers | `pkgs.tex` + `conf.tex` | 3 cm margins (`geometry`), `fancyhdr` headers with the group number, centered page number |
| Chapter headings | `conf.tex` | `titlesec` customizations; the **later** `\titleformat{\chapter}` definition takes precedence |
| Theorem boxes | `cmds.tex` | `amsthm` declarations plus a redefined `leftbar` frame with `myGray` fill |
| Formal AAU title page | `titlepage.tex` + `ext/aautitlepage.sty` | `\aautitlepage` and `\projectinfo`, with a separate abstract input |


## Custom command reference

All the commands below are defined in [`incl/pre/cmds.tex`](incl/pre/cmds.tex), unless noted. They are shortcuts for **LaTeX math/source code**, not terminal commands. The original source contains a few deliberate overrides and some names reused later in the same file; the table describes the **effective final meanings**.

### Mathematical notation and operators

| Command | Output / role | Example |
|---|---|---|
| `\tw{...}` | White text via `\textcolor{white}{...}` | `\tw{hidden on blue}` |
| `\phm` | Width-preserving invisible minus sign, `\phantom{-}` | `$\phm x$` |
| `\Tophat{z}` | Hatted variable, `\hat{z}` | `$\Tophat{\theta}$` |
| `\ti{x}` | Tilde accent, `\widetilde{x}` | `$\ti{X}$` |
| `\a`, `\epsi` | `\alpha`, `\varepsilon` | `$\a+\epsi$` |
| `\gets` | Assignment symbol `:=` (redefines the normal `\gets` arrow) | `$x\gets 1$` |
| `\trk` | Gradient symbol `\nabla` | `$\trk f$` |
| `\m`, `\*` | Multiplication dot `\cdot` | `$a\m b$` |
| `\bigO`, `\BO` | Calligraphic big-O `\mathcal{O}` | `$\bigO(n^2)$` |
| `\ud` | Literal differential element `\,\mathrm{d}x` | `$\int f(x)\ud$` |
| `\e` | Roman letter e (`\text{e}`) | `$\e^x$` |
| `\PP` | Text `P` | `$\PP(A)$` |
| `\Sym`, `\Isom`, `\rank` | Text operators `Sym`, `Isom`, `rank` | `$\rank(A)$` |
| `\tr{A}` | Trace as `\text{tr}(A)` | `$\tr{A}$` |
| `\var` | Lowercase text `var` | `$\var(X)$` |
| `\indep`, `\independent` | Two definitions of a statistical-independence symbol | `$X\indep Y$` |
| `\checkmark` | Custom TikZ tick mark (overrides the standard checkmark) | `$\checkmark$` |



### Blackboard bold, calligraphic sets, and spaces

| Commands | Expansion |
|---|---|
| `\R`, `\F`, `\C`, `\Z`, `\N`, `\ML`, `\K`, `\Q` | `\mathbb{R}`, `\mathbb{F}`, `\mathbb{C}`, `\mathbb{Z}`, `\mathbb{N}`, `\mathbb{L}`, `\mathbb{K}`, `\mathbb{Q}` |
| `\disneyd`, `\Lag`, `\E`, `\M`, `\T`, `\A`, `\cp` | `\mathcal{D}`, `\mathcal{L}`, `\mathcal{E}`, `\mathcal{M}`, `\mathcal{T}`, `\mathcal{A}`, `\mathcal{P}` |
| `\NA` | `\mathcal{N}_A` |


### Vectors, norms, and products

| Commands | Expansion / role |
|---|---|
| `\x`, `\y`, `\v`, `\w`, `\u`, `\b`, `\t` | Bold vectors `\bm{x}`, `\bm{y}`, `\bm{v}`, `\bm{w}`, `\bm{u}`, `\bm{b}`, `\bm{t}` |
| `\0` | Bold zero `\bm{0}` |
| `\om` | Bold omega `\bm{\omega }` |
| `\norm{z}` | `\left\lVert z\right\rVert` |
| `\fnorm{A}` | `\left\lVert A\right\rVert_F` |
| `\ip{x}` | `\left\langle x\right\rangle` (one argument; not a two-argument inner-product macro) |
| `\vecto{a}{b}` | 2-row column vector, `bmatrix` |
| `\vectre{a}{b}{c}` | 3-row column vector, `bmatrix` |
| `\prik` | Custom reduced-size centered bullet (dot-product symbol) |




### Fixed derivatives and specialized variable shortcuts


| Command | Expansion |
|---|---|
| `\df` | `\frac{\partial f}{\partial x}` |
| `\dx` | $\frac{d x}{d t}$ |
| `\Dt` | `\frac{\mathrm{d}x}{\mathrm{d}t}(t)` |
| `\D` | `\frac{\mathrm{d}x}{\mathrm{d}t}` |
| `\Dx` | `\frac{\mathrm{d}X}{\mathrm{d}t}` |
| `\DP` | `\frac{\mathrm{d}\Phi}{\mathrm{d}t}` |
| `\Dp` | `\frac{\mathrm{d}\phi}{\mathrm{d}t}` |
| `\Dif{z}` | `\frac{\mathrm{d} z}{\mathrm{d}t}` |
| `\xt` | `\widetilde{x}_{\tau}^\ast` |
| `\xu` | `x_{\tau}^\ast` |
| `\xtan` | `\widetilde{x}^{\phantom{}TAN}` |


### Probability and statistics

| Command | Expansion | Example |
|---|---|---|
| `\Var{X}` | `\text{Var}\left[{X}\right]` | `$\Var{X}$` |
| `\Cov{X,Y}` | `\text{Cov}\left[{X,Y}\right]` | `$\Cov{X,Y}$` |
| `\Ex{X}` | `\text{E}\left[{X}\right]` | `$\Ex{X}$` |


## Theorems and custom environments

The base environments are declared in [`cmds.tex`](incl/pre/cmds.tex) 
| Environment | Printed type | Notes |
|---|---|---|
| `thm` | Theorem | Chapter-based numbering |
| `lem` | Lemma | Same counter as `thm` |
| `propo` | Proposition | Same counter as `thm` |
| `cor` | Corollary | Same counter as `thm` |
| `defn` | Definition | Same counter as `thm` |
| `conj` | Conjecture | Same counter as `thm` |
| `exmp1` | Example | Ends with an open square |
| `met` | Method | Same counter as `thm` |
| `bema` | Remark | Unnumbered |
| `bevis` | **Proof** | Custom `beviss` style; ends with a filled square |
| `modstrid` | Bevis | Custom `beviss` style; ends with a lightning symbol |

Nine wrappers provide preformatted bars or boxes around base theorem environments:

| Wrapper | Underlying environment | Appearance |
|---|---|---|
| `theo{...}` | `thm` | Black bar on pale `myGray` background |
| `lemma{...}` | `lem` | Black bar on pale `myGray` background |
| `defi{...}` | `defn` | Black bar on pale `myGray` background |
| `pro{...}` | `propo` | Black bar on pale `myGray` background |
| `prop{...}` | `propo` | Another wrapper for propositions, same style |
| `koro{...}` | `cor` | Black bar on pale `myGray` background |
| `meto{...}` | `met` | Gray bar on pale `myGray` background |
| `ex{...}` | `exmp` → `exmp1` | Thin gray bar on white background |
| `exmp{...}` | `exmp1` | Example without the outer `leftbar` frame |

Each wrapper takes **one mandatory argument**, which is inserted as the first text in the theorem body; it is **not** an optional theorem title. Pass `{}` if you do not want introductory text:

```latex
\begin{theo}{Fundamental property.}
Let $f:\R\to\R$ be continuous. Then the desired claim follows.
\end{theo}

\begin{bevis}
We verify the conditions one by one.
\end{bevis}

\begin{ex}{Worked example.}
Consider $\x=\vecto{1}{2}$.
\end{ex}
```

## Practical examples

### A chapter with equations and a theorem

Create `incl/main/Introduction.tex`:

```latex
\chapter{Introduction}
\section{Motivation}
Let $f:\R^n\to\R$. We write the gradient as $\trk f$.

\begin{defi}{Euclidean norm.}
For $\x\in\R^n$, the Euclidean norm is $\norm{\x}$.
\end{defi}

\begin{theo}{}
If $\x=\0$, then $\norm{\x}=0$.
\end{theo}
```

Include it after `\mainmatter` in `master.tex`:

```latex
\mainmatter
\include{incl/main/Introduction}
```

Remove or replace `\include{incl/main/Start}` if you do not need it.

### A Python code listing

```latex
\begin{lstlisting}[language=Python,style=custompy,caption={Simple example},label={lst:example}]
def square(x):
    return x ** 2
\end{lstlisting}

See Listing~\ref{lst:example}.
```

The `custompy` style is defined in `conf.tex`, while an alternative `mystyle` is defined in `cmds.tex`. For external source files, use `\lstinputlisting[language=Python,style=custompy]{code/example.py}` after actually adding that file. Listings display code; **they do not execute it**.

### A figure and a TikZ diagram

```latex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=.6\linewidth]{fig/img/my-figure.pdf}
  \caption{Example figure.}
  \label{fig:example}
\end{figure}
```

Add `fig/img/my-figure.pdf` yourself; it is a sample filename, not a pre-existing repository image. For drawings, `tikz` and several libraries are already loaded. The cover badge is a real example of the project's TikZ `\input` pattern.

### Citations and the bibliography

Add a BibTeX entry to one of [`books.bib`](incl/bib/books.bib), [`articles.bib`](incl/bib/articles.bib), or [`software.bib`](incl/bib/software.bib), and cite it with the loaded `natbib` package:

```latex
A textual citation: \citet{your-key}.
A parenthetical citation: \citep{your-key}.
```

The existing end of `master.tex` uses:

```latex
\backmatter
\bibliographystyle{apalike}
\bibliography{incl/bib/books,incl/bib/articles,incl/bib/software}
```

Use a real BibTeX key; `your-key` is only an illustration. `latexmk` normally runs the necessary BibTeX passes when citations are present.

