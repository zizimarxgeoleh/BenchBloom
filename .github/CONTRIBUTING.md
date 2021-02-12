# Contributing to BenchBloom

Thanks for considering a contribution. BenchBloom is a forensic herbarium for
benchmark contamination: it reads text corpora, presses them flat and compares
their spore prints. It never executes anything it reads and makes no network
calls.

## Development setup

- **Python 3.8+** - the orchestrator lives in `benchbloom/` and uses the
  standard library only. There is nothing to install.
- **A C++17 compiler** (`g++` or `clang++`) - the microscope lives in
  `cpp/bloomdex.cpp` and is built directly, no CMake.

```bash
python -m compileall -q benchbloom
make                       # or: bash cpp/build.sh
python -m benchbloom scan \
  --ref examples/benchmark.jsonl \
  --subject examples/training.jsonl \
  --field text --ngram 4 --threshold 0.3
```

## Before you open a pull request

1. `python -m compileall -q benchbloom` must pass and the example `scan` above
   must keep flagging `b1`, `b2` and `b4`.
2. The C++ engine must still compile cleanly if you touched `cpp/`:
   `g++ -std=c++17 -O2 -Wall -Wextra -pedantic cpp/bloomdex.cpp -o cpp/bloomdex`
3. Keep the package dependency-free; standard library only.
