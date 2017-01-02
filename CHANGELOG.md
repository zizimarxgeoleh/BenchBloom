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

