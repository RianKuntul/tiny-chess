# tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/RianKuntul/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/RianKuntul/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in at most 4,096 bytes of Python, written for the
make.fun **tiny-chess-01** competition
([bounty page](https://make.fun/bounty/tiny-chess-01)).

`main.py` is the whole engine (packed from a readable source with the
kit's `makefun compress`): a deterministic negamax search — alpha-beta
with PVS, quiescence (captures, promotions and check evasions), a
transposition table, killer and history move ordering, null-move
pruning, late-move reductions and check extensions — over a tapered
piece-square-table evaluation. It searches to a fixed cap of 65,000
nodes per move and never reads a clock, so every replayed trial makes
the same moves. Positions already seen in the game score as draws in
search, which keeps it from shuffling into threefold repetitions.

On the kit's three 6-game practice trials it scored Elo 1545, 1364
and 1451 (11 wins, 2 draws, 5 losses in all), above the house
baseline's practice mean. It plays its games through the competition
env over HTTP.

MIT licensed — see `LICENSE`.
