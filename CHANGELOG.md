# Changelog

All notable changes to `fancytests` are listed here.
Versions follow [semantic versioning](https://semver.org): a new major
version may change existing commands; minor versions only add features.

## [2.0] — 2026-10-09

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
