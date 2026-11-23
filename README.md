# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/jenalsosmed-sudo/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/jenalsosmed-sudo/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

Build the strongest chess engine in 4 KB of Python, for make.fun's
[tiny-chess-01](https://make.fun/bounty/tiny-chess-01) bounty — $500 in USDC
over 20 places ($100 for 1st, $70 for 2nd, $50 for 3rd, $20 for 4th–10th,
$14 for 11th–20th).

`main.py` (4,057 bytes) is the whole engine: a 0x88 board, negamax
alpha-beta with quiescence search over captures and promotions (delta
pruning, check evasions), a transposition table, MVV-LVA move ordering,
incremental piece-square evaluation, and iterative deepening to a fixed
80,000-node budget per move — fully deterministic, no clock,
no randomness, no network except the trial env. The source is packed
with LZMA (the unpacker and payload both count toward the 4,096-byte
cap). It plays the 8-game gauntlet through the env at `MAKEFUN_ENV_URL`.

Local checks: perft(3) 8,902 (startpos) and 97,862 (Kiwipete) exact;
12–0 vs the kit's greedy starter, all by checkmate; practice trial 0
on the kit's own env + official scorer: Elo 1099 (1W 2D 3L — beat
depth-3 as black, drew depth-2 and depth-4; first version scored
Elo 876 at 50,000 nodes).
