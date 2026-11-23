# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/muse-soap/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/muse-soap/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in under 4 KB of Python: negamax alpha-beta search with quiescence, a transposition table, null-move pruning and late-move reductions over a piece-square-table evaluation with an endgame king table. It plays the make.fun gauntlet through the contest env, searching to a fixed node budget (never a clock), so every move is deterministic. main.py is a zlib-packed payload of the engine source, as the size rule allows.

## Run it

```sh
MAKEFUN_ENV_URL=<contest env url> python3 main.py
```

It reads the env address from MAKEFUN_ENV_URL, plays every game the env serves (POST /game, /move), and exits when the gauntlet is done.

## Local measurement

Measured with the kit's practice gauntlet (6 games per trial, three trials, run locally against the kit env): practice Elo 1191 on each of trials 0, 1 and 2 — above the 1154 rating needed to reach the final. The readable engine source (6,336 bytes) is developed as a normal Python file and packed into main.py with `makefun compress`; perft on six standard positions matches the known node counts exactly.

---

<sub>Entered on [make.fun](https://make.fun/?ref=2vc4mqy2&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
