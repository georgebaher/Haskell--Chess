# TheChessWizard
TheChessWizard is a fun and interactive Haskell-based chess engine designed for playing and experimenting with chess moves. This project allows you to initialize and visualize a chess board, validate legal moves for pieces, suggest possible moves, and execute moves (if legal) on the board and visualize the board's new state.

## Features
**Visualize Board:** Display the current state of the board with pieces represented by their initials and suffixed with 'W' or 'B' for White and Black respectively.\
**Move Validation:** Check if a move is legal for a given piece.\
**Move Suggestion:** Get a list of possible legal moves for a piece.\
**Move Execution:** Execute a move if it's legal and update the board state.\

## Usage
Here are some sample queries with their expected results to help you get started:

### Visualize Board

```
> visualizeBoard (Black, [N ('d',6), B ('e',6), B ('f',4), N ('f',3), P ('h',2),P ('g',2), Q ('e',2),
P ('c',2), P ('b',2), P ('a',2), K ('c',1), R ('d',1),R ('h',1)],
[Q ('a',8), B ('e',8), R ('f',8), K ('g',8), P ('e',7), B ('g',7), P ('h',7),
P ('g',6), N ('h',6), P ('c',5), P ('f',5), P ('a',4), P ('b',4)])
  a    b    c    d    e    f    g    h
8 | QB |    |    |    | BB | RB | KB |    |
7 |    |    |    |    | PB |    | BB | PB |
6 |    |    |    | NW | BW |    | PB | NB |
5 |    |    | PB |    |    | PB |    |    |
4 | PB | PB |    |    |    | BW |    |    |
3 |    |    |    |    |    | NW |    |    |
2 | PW | PW | PW |    | QW |    | PW | PW |
1 |    |    | KW | RW |    |    |    | RW |

Turn: Black
```

### Check Legal Move

```
> isLegal (N ('e',7)) (White, [N ('d',4),P ('f',4),P ('b',3),K ('a',1)],
[N ('f',5),N ('e',7),P ('d',7),K ('c',7),P ('b',5),P ('a',3)]) ('f',5)
False

> isLegal (P ('h',2)) (White, [P ('h',2),K ('c',1)], []) ('h',4)
True

> isLegal (Q ('d',4)) (Black, [Q ('d',4),P ('f',4),P ('b',3),K ('a',1)],
[N ('f',5),R ('e',7),P ('d',7),K ('c',7),P ('b',5),P ('a',3)]) ('d',7)
True
```

### Suggest Moves

```
> suggestMove (N ('d',4)) (White,
[R ('h',1),N ('g',1),B ('f',1),K ('e',1),Q ('d',1),B ('c',1),N ('b',1),R ('a',1),
P ('h',2),P ('g',2),P ('f',3),P ('e',2),P ('d',2),P ('c',2),P ('b',3),P ('a',2)],
[R ('h',8),N ('d',4),B ('f',8),K ('e',8),Q ('d',8),B ('c',8),N ('b',8),R ('a',8),
P ('h',7),P ('g',7),P ('f',7),P ('e',7),P ('d',7),P ('c',6),P ('b',7),P ('a',7)])

[('b',3),('b',5),('c',2),('e',2),('e',6),('f',3),('f',5)]

> suggestMove (B ('c',1)) (White,
[R ('h',1),N ('g',1),B ('f',1),K ('e',1),Q ('d',1),B ('c',1),N ('b',1),R ('a',1),
P ('h',2),P ('g',2),P ('f',3),P ('e',2),P ('d',2),P ('c',2),P ('b',3),P ('a',2)],
[R ('h',8),N ('d',4),B ('f',8),K ('e',8),Q ('d',8),B ('c',8),N ('b',8),R ('a',8),
P ('h',7),P ('g',7),P ('f',7),P ('e',7),P ('d',7),P ('c',6),P ('b',7),P ('a',7)])

[('a',3),('b',2)]
```

### Execute Move

```
> move (N ('h',6)) ('f',7) (Black,
[N ('d',6), B ('e',6), B ('f',4), N ('f',3), P ('h',2),P ('g',2), Q ('e',2),
P ('c',2), P ('b',2), P ('a',2), K ('c',1), R ('d',1),R ('h',1)],
[Q ('a',8), B ('e',8), R ('f',8), K ('g',8), P ('e',7), B ('g',7), P ('h',7),
P ('g',6), N ('h',6), P ('c',5), P ('f',5), P ('a',4), P ('b',4)])

(White,[N ('d',6),B ('e',6),B ('f',4),N ('f',3),P ('h',2),P ('g',2),
Q ('e',2),P ('c',2),P ('b',2),P ('a',2),K ('c',1),R ('d',1),R ('h',1)],
[Q ('a',8),B ('e',8),R ('f',8),K ('g',8),P ('e',7),B ('g',7),P ('h',7),
P ('g',6),N ('f',7),P ('c',5),P ('f',5),P ('a',4),P ('b',4)])
```

### Illegal Move Attempt

```
> move (P ('f',5)) ('h',8) (Black,
[N ('d',6), B ('e',6), B ('f',4), N ('f',3), P ('h',2),P ('g',2),
Q ('e',2), P ('c',2), P ('b',2), P ('a',2), K ('c',1), R ('d',1),
R ('h',1)],
[Q ('a',8), B ('e',8), R ('f',8), K ('g',8), P ('e',7), B ('g',7),
P ('h',7), P ('g',6), N ('h',6), P ('c',5), P ('f',5),
P ('a',4), P ('b',4)])

Program error: Illegal move!
```

## Setup
Clone the repository and load the Haskell file in your preferred Haskell environment. Ensure you have the necessary Haskell setup to run and test the functions.

Enjoy your chess games with TheChessWizard brought to you by Mr Haskell the functional!
