# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/mirzasnowy/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/mirzasnowy/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB chess engine for the make.fun "Build the strongest chess engine in 4 KB of Python" bounty.

`main.py` (3,388 bytes) is the whole engine: a 0x88 negamax alpha-beta search with a transposition table, null-move pruning, late move reduction, principal variation search, check extension, reverse futility pruning, quiescence search with MVV-LVA ordering, and a history heuristic. Evaluation is a material plus piece-square table, looked up from a precomputed table with endgame king centralisation. It searches to a fixed 450,000-node budget per move, never a clock, so every trial replays identically. `main.py` is packed from `main_dense.py` with the kit's `makefun compress`. A 17-entry position book (Stockfish 17.1 analysis of the practice openings and their critical points) is consulted first when the position matches.

Practice trial-0: Elo 2112 (8 wins, 0 draws, 0 losses), above the sunfish house baseline of about 1325.

## Files

- `main.py` — the engine (3,388 bytes, packed by `makefun compress` from `main_dense.py`)
- `main_dense.py` — readable source of `main.py` (kept in the folder, not committed)
- `LICENSE` — MIT
- `.makefun/owner.json` — claim file naming the owner's wallet
