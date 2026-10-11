# A note on MinHash variance

The engine's estimate is the fraction of matching minima, so its standard
error shrinks roughly with `1/√K`. Treat every flagged pair as a candidate:
confirm the pairs that matter with the exact `scan` before acting on them.
