# tiny-chess-01

A 4 KB chess engine for the make.fun "Build the strongest chess engine in 4 KB of Python" bounty.

`main.py` (3,201 bytes) is the whole engine: a 0x88 negamax alpha-beta search with a transposition table, null-move pruning, late move reduction, principal variation search, check extension, reverse futility pruning, quiescence search with MVV-LVA ordering, and a history heuristic. Evaluation is a material plus piece-square table, looked up from a precomputed table with endgame king centralisation. It searches to a fixed 450,000-node budget per move, never a clock, so every trial replays identically. `main.py` is packed from `main_dense.py` with the kit's `makefun compress`.

Practice trial-0: Elo 1464 (3 wins, 3 draws, 2 losses), above the sunfish house baseline of about 1325.

## Files

- `main.py` — the engine (3,201 bytes, packed by `makefun compress` from `main_dense.py`)
- `main_dense.py` — readable source of `main.py` (kept in the folder, not committed)
- `LICENSE` — MIT
- `.makefun/owner.json` — claim file naming the owner's wallet
