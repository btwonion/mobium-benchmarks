# Mobium benchmark data

Raw data of [Mobium](https://github.com/btwonion/mobium)'s benchmark rounds. The protocol, the setups A–D and the
results with their analysis are in Mobium's
[`docs/benchmarks.md`](https://github.com/btwonion/mobium/blob/main/docs/benchmarks.md); every gate in its `PLAN.md` is
decided there.

One folder per round: `<yyyy-mm-dd>-<machine>/` (a second round of the day appends `-<build>`), with a folder per
setup (`A`–`D`) holding what `/mobium bench` wrote to `<game dir>/mobium-bench/`:

- `summary.csv`: one row per run (frame times, stage timers, build, display, power, GPU clock)
- `suite-*.csv`, `gatea-*.csv`, `gateb-*.csv`, `gatec-*.csv`, `stages-*.csv`: the medians of `/mobium suite`, the
  gates and `/mobium stages`
- `<scene>-<setup>-<yyyymmdd-hhmmss>.csv.gz`: every frame of one run, gzipped

`python3 benchmark/bench_round.py` in Mobium's repository writes a round here and commits and pushes it. Rounds
measured by hand are copied in with the same layout.

## Players' files

`players/<yyyy-mm-dd>-<machine>/` holds one `/mobium benchmark` file each, as the player sent it (GitHub issues with
the label `benchmark`, Discord): the medians of Mobium off and on per scene, the gains and the machine. Their results
are in Mobium's `docs/benchmarks.md`, *Players' results*, which names the issue each file came from.

## Commit ids from before the history rewrite

On 27 Oct 2026 these files were removed from Mobium's history, which gave almost every Mobium commit a new id. Ids
from before that day (the `build` column, `mobium-build.properties` in older jars, `docs/benchmarks.md`) name the old
commits; [`commit-map.txt`](commit-map.txt) gives the new id for each old one: `grep ^8d26a26 commit-map.txt`.
