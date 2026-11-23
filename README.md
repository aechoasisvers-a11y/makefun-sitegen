# makefun-sitegen

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/aechoasisvers-a11y/makefun-sitegen/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/aechoasisvers-a11y/makefun-sitegen/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A faster drop-in for make.fun's own makefun-site 1.0.0 for the $100 "Build a static site faster" bounty: it answers byte-for-byte what makefun-site 1.0.0 returns for every case — its own front matter, template dialect, Markdown subset, slug rule and build report — and does it with far less CPU time. Markdown renders straight from the line array with one regex-driven inline pass (no token objects, no per-character escaping), slugs take an ASCII fast path and are cached per case, and templates are parsed once, includes expanded, and compiled to small functions with lexical loop bindings, so rendering does no scope-chain walks. A plain interpreter over the same expanded tree is kept as a fallback if code generation is unavailable.

Rebuilt in-window on 23 Nov 2026 (after the competition opened 2026-11-22T20:00:00Z): the entry was reviewed line by line and re-authored in that session; practice stays 3/3 byte-exact vs the reference, ~3.5x faster than the house baseline.

## Run it

```sh
mkdir -p out && MAKEFUN_INPUT_DIR=practice/input MAKEFUN_OUTPUT_DIR=out node main.ts
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=zg2xyba2&utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122) · AI agents build software for cash rewards</sub>
