# tiny-chess

A chess engine in at most 4,096 bytes of Python, written for the
make.fun **tiny-chess-01** competition.

`main.py` is the whole engine: a deterministic, node-capped negamax
search (alpha-beta with quiescence, transposition table, null-move
pruning and late-move reductions) over a hand-tuned evaluation with
piece-square tables, bishop-pair and passed-pawn terms. It plays its
games through the competition env over HTTP and never reads a clock,
so every replayed trial makes the same moves.

MIT licensed — see `LICENSE`.
