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

