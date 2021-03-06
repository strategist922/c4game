# c4game

An R package to provide a simple model of the popular family game Connect 4.

[![Travis-CI Build Status](https://travis-ci.org/sellorm/c4game.svg?branch=master)](https://travis-ci.org/sellorm/c4game) [![Codecov](https://img.shields.io/codecov/c/github/sellorm/c4game.svg)](https://codecov.io/gh/sellorm/c4game/)

## Installation

```
source("https://install-github.me/sellorm/c4game")
```

...or, if you prefer...

```
devtools::install_github("sellorm/c4game")
```


## Usage

To play a game against the random bot using the built in REPL ("q" quits):

```
c4repl()
```

To play a game against another human:

```
c4repl(2)
```

To let the computer play against itself in a random game:

```
repl(0)
```

To create your own game object to play with:

```
game <- c4game$new(board = matrix(, nrow = 6, ncol = 7), player = 1)
```

This creates a new object called `game` that you can then interact with.

The `game` object will have the following fields:

* **board** The current state of the game board
* **gamestate** Usually just set to 'next' but will report if a win is detected
* **player** The current player, 1 or 2

The `game` object only has one method, `dropToken`. It takes a single parameter, n, where n is the number of the column the token should be dropped into.

For example:

```
game$dropToken(3)
```

Would drop a token into column 3 for the current user in `game$player`.

At this point, `game$board` will update, `game$gamestate` will report either `next` for "next move" or "Player x wins!", and `game$player` also updates to reflect the current player number, either 1 or 2.

# License

MIT © Mark Sellors
