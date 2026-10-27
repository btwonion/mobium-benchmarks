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
