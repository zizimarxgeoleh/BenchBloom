# Changelog

All notable changes to BenchBloom are documented here. The format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and the project
adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

_Next patch notes are being collected here._

## [5.3.0] - 2026-08-18

### Added
- `--engine` on `index` to point at a `bloomdex` binary explicitly, and
  `--workdir` to keep the normalized and signature intermediates for review.
- `--seed` passthrough documented as the deterministic splitmix64 stream that
  makes spore prints reproducible across machines.

### Changed
- Short records (fewer tokens than `--ngram`) degrade to a single shingle
  instead of dropping out of the assay.

### Fixed
- `report` lists the top overlaps by estimated Jaccard instead of file order.

## [4.2.0] - 2025-10-07

### Added
- Worked examples (`examples/benchmark.jsonl`, `examples/training.jsonl`) plus
  an end-to-end walkthrough in `examples/README.md`.
- CI runs the full `index` / `report` assay on every push.

### Changed
- The README states plainly what is finished and what is planned, and the
  ROADMAP keeps the same honest ledger.

## [3.0.0] - 2024-09-24

### Changed
- Signature files are plain text by design: one record per line, K
  space-separated 64-bit minima, inspectable with any tool.
- `bloomdex` streams the corpus so a specimen larger than memory still fits
  on the slide.

## [2.1.0] - 2023-11-14

### Added
- `report` subcommand rendering a saved `match.tsv` into a human summary.
- JSON summary fields: contaminated reference items, contamination rate and
  peak overlap.

### Changed
- The verdict grading (`CLEAN`, `TRACE`, `ELEVATED`, `HEAVY`) applies to both
  the exact `scan` and the engine-backed `index` paths.

## [1.0.0] - 2022-11-08

### Added
- Stable CLI contract: `normalize`, `scan`, `index`, `report`.
- `--top` keeps only the strongest pairs in the JSON scan report and
  `--jaccard-only` switches the trigger metric back to Jaccard.

## [0.9.0] - 2022-03-15

### Added
- `bloomdex self` finds near-duplicate records inside a single signature set,
  which turns the microscope into a deduplication pass for one corpus.

## [0.8.0] - 2021-07-20

### Added
- `--k` signature width, `--ngram` shingle size and `--min-token` filters on
  the engine commands.
- Deterministic splitmix64 seeding so two runs on two machines produce
  identical signatures.

## [0.7.0] - 2020-11-03

### Added
- `index` orchestrates the full assay: normalize, sign and match through the
  C++ engine, with a graceful error when the binary is missing.
- Streamed line processing in `bloomdex` so input size is not bounded by RAM.

## [0.6.0] - 2020-02-11

### Added
- `bloomdex match` scores candidate overlap between two signature sets and
  writes a tab-separated report.
- `--threshold` filters matches on estimated Jaccard.
