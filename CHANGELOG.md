# Changelog

All notable changes to `fancytests` are listed here.
Versions follow [semantic versioning](https://semver.org): a new major
version may change existing commands; minor versions only add features.

## [1.2.0] — 2026-10-16

### Added
- `\testsetup{margin-mark=side|below}`: with `mcq=margin`, the motivation mark
  can go centred below the score box (`below`) instead of on its left
  (`side`, default).

## [1.1.0] — 2026-10-16

### Added
- Answer table for multiple-choice questions, `\answergrid`: a compact band of
  three rows (question labels, answer cell with a small motivation mark in its
  corner, score box) with the total at the end. Lists every multiple-choice
  question of the copy in printed order, following shuffling and reduced
  versions; continues on a second line when the questions do not fit.
- Motivation mark filled in by students: tick = motivated on the test,
  F = motivated on a separate sheet. Three looks,
  `\testsetup{motivation-mark=line|below|label}` (default `below`: a short
  grey line with a tiny M underneath).
- Three frames for the answer table, `\testsetup{grid-frame=cells|rules|lines}`
  or `\answergrid[frame=...]` (default `rules`: horizontal rules only).
- `\testsetup{mcq=band}`: multiple-choice points only in the answer table.
  `\testsetup{mcq=margin}`: motivation mark next to each multiple-choice score
  box, with a one-line legend printed once per copy.
- Optional motivation space after the options: `motivation=<lines>`,
  `motivation-style=blank|grid`, settable per test, exercise, question or
  `choices`.
- Correction strips in the teacher copy (`answers`): one strip per copy with
  the correct letters, aligned with the student answer table.
- `\answergrid[style=boxes]`: one row per question with lettered boxes
  (`exercise`, `cols`, `title`, `before`, `after` keys).
- `labels=boxed`: option letters inside small boxes.

### Fixed
- Question options (`pts`, `diff`, `mark`, `upper`) lost in multi-column
  `parts` after the first question.
- Reduced version: omitted questions no longer appear in the answer key;
  no "missing \item" error when the first or all questions of a `parts` are
  omitted.
- Score boxes in multi-column `parts` aligned with the right margin.

## [1.0] — 2026-10-09

First release of `fancytests`, the streamlined successor of the test part of
`fancylessons`.

### Added
- Key–value syntax for every command and environment (no more `( ) < > | |`
  delimiters).
- `\testsetup` for document-wide settings; `\testheader` with Italian key
  aliases (`materia`, `classe`, `data`, `titolo`, …).
- Compact header (`style=compact`): grey separators, closing rule, automatic
  title placement (`titlebreak=auto|always|never`).
- `parts` environment with `cols`, `stretch`, `start`, `ragged`; questions with
  `pts`, `diff`, `mark`, `upper`, `noreduced`.
- Reduced (DSA) versions from the same source (`\testsetup{reduced}`).
- `choices` environment replacing all `\random…options` macros: automatic
  columns, `\correct`, `\choice[fixed]`, `\correct[if={v=2}]`, letter labels,
  spacing keys `before`, `rowsep`, `after`.
- Answer key exported to `<document>.key.csv`; teacher copy with the
  `answers` option or `\testsetup{answers}`; `solution` environment.
- Reproducible randomisation with one seed (`seed=`, `\setseed`): `\pick`,
  `\randint`, `\useval`, `shuffle` / `\shuffled`, shuffled questions
  (`parts[shuffle]`, `fixed`, `follow`) and exercises (`exercises`).
- Automatic exercise closing, bonus exercises, `\finalscore` styles `table`,
  `compact`, `formula`, `minimal`; configurable grade formula.
- `ftplot` / `\fplot` with a photocopy-friendly graph style; TikZ styles for
  physics diagrams (`force`, `velocity`, `spring`, `ground`, `continue`, …).
- Speed options: `nofigures` (draft), `cache` (memoize), `plots=false`,
  `units=false`.
- `legacy` option: tests written with `fancylessons` compile unchanged.

### Changed
- Package load time about 0.8 s instead of 1.9 s (`fancylessons`).
- Score boxes use the decimal point by default (`decimal=` to change).
