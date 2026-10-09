# fancytests

A LaTeX package for writing maths and physics tests for Italian secondary
schools (*verifiche*): headers with DSA options, exercises and questions with
automatic score totals, shuffled multiple-choice questions with an exported
answer key, reproducible variants, reduced versions and teacher copies — from
a single source file.

It replaces the test-related part of `fancylessons` (the author's earlier
package, used for both lesson notes and tests), loads about twice as fast, and
uses a `key=value` syntax throughout. References to `fancylessons` in the
manual and in the `legacy` option are mainly for the author, to compare the old
and new versions and reuse past tests.

**Manual:** [`docs/fancytests-doc.pdf`](docs/fancytests-doc.pdf) · **Repository:** <https://github.com/Bradwave/fancytests>

## Quick start

```latex
\documentclass[10pt]{article}
\usepackage[seed=2026]{fancytests}

\testsetup{class=4M, subject=math, style=compact}

\begin{document}
\testheader[date=20/03/2026, title={Logaritmi}]

\exercise Risolvi le seguenti equazioni.
\begin{parts}[cols=2]
  \itemx[pts=1] $3^x = 9$
  \itemx[pts=1] $\log_2 x = 3$
\end{parts}

\exercise Rispondi.
\begin{parts}
  \itemx[pts=1] Quale funzione è sempre crescente?
    \begin{choices}
      \correct $e^x$
      \choice  $e^{-x}$
      \choice[fixed] Nessuna delle precedenti
    \end{choices}
\end{parts}

\vfill
\finalscore
\end{document}
```

## Installation

`fancytests` is a single file, [`fancytests.sty`](fancytests.sty). Put it next
to your `.tex` file.

**Overleaf.** In your project choose *Upload → From external URL* and paste

```
https://raw.githubusercontent.com/Bradwave/fancytests/main/fancytests.sty
```

Overleaf keeps a linked copy: the *Refresh* button downloads the latest
version. To freeze a project on a specific release (recommended for tests
already given), use a tag instead of `main`, e.g. `…/fancytests/v1.0/fancytests.sty`.

Requires TeX Live 2023 or later (on Overleaf: *Menu → Settings → TeX Live
version*).

## Examples

| File | Shows |
|---|---|
| [`01-verifica-matematica`](examples/01-verifica-matematica.tex) ([PDF](examples/01-verifica-matematica.pdf)) | Full header, questions in columns, graphs, multiple choice with variants, bonus exercise |
| [`02-verifica-fisica`](examples/02-verifica-fisica.tex) ([PDF](examples/02-verifica-fisica.pdf)) | Compact header with DSA boxes and a long title, units, physics diagram, score table |
| [`03-copie-e-correzione`](examples/03-copie-e-correzione.tex) ([PDF](examples/03-copie-e-correzione.pdf)) | Several shuffled copies, answer key, teacher copy, reduced version |
| [`04-sintassi-fancylessons`](examples/04-sintassi-fancylessons.tex) ([PDF](examples/04-sintassi-fancylessons.pdf)) | Old `fancylessons` syntax with the `legacy` option |

To compile an example locally, run `latexmk -pdf` inside `examples/` (the
included `.latexmkrc` finds `fancytests.sty` in the parent folder) or copy
`fancytests.sty` next to it.

## Main features

- **Header** — full or compact, DSA boxes (`dsa=dsa|rid`), times, resit date.
- **Scores** — per question (`pts`), per exercise, bonus, final table and grade
  formula, computed automatically.
- **Multiple choice** — `choices` with automatic columns, shuffled options,
  fixed last option, answers that depend on a variant.
- **Answer key** — `<document>.key.csv` with the correct letter for every copy.
- **Randomisation** — one reproducible seed for options, questions, exercises,
  variants (`\pick`) and numbers (`\randint`).
- **Versions** — several copies (`\Repeat`), reduced DSA version
  (`noreduced`), teacher copy (`answers`).
- **Graphs and diagrams** — `ftplot` and TikZ styles for physics.
- **Speed** — `nofigures` draft mode and `cache` for figures.
- **Compatibility** — `legacy` option for tests written with `fancylessons`.

## Credits

Written by Matteo Bramardi, co-authored with
[Claude](https://www.anthropic.com/claude) (Anthropic), which wrote and tested
most of the code under the author's direction.

## Licence

Copyright © Matteo Bramardi. Distributed under the
[LaTeX Project Public License 1.3c](https://www.latex-project.org/lppl/lppl-1-3c/)
or later.
