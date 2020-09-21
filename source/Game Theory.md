# Game Theory

### Arjun Vikram, SEM AMC Club

![xkcd 1287](https://www.explainxkcd.com/wiki/images/6/65/puzzle.png)

<center>Both Go and Chess are combinatorial games! <i>(Source: xkcd)</i></i></center>

## Introduction

Game Theory is the study of combinatorial games and their optimal strategies. It was pioneered by John Nash, who went on to win the Nobel Prize in Economic Sciences for his research!

For the purposes of this lesson, a **combinatorial game** is a game for two players which satisfies the following conditions:

- **Non-probabilistic**: Games where the outcome depends on luck are not considered combinatorial games. Probabilistic games are also studied using similar techniques, however for today we are only considering combinatorial games.
- **Perfect information for both players**: Games where both players don't have complete information about the current state are not considered combinatorial. For example, games where players are dealt cards that only they can see are not combinatorial.
- **Win or lose outcome**: Games where players can tie or continue gameplay infinitely are not combinatorial.

Advanced game theory studies may relax some of these assumptions, however today is meant to be only a brief introduction.

In the field of game theory, you assume both players are perfect logicians who will play with the best possible strategy. Because of this, you can determine whether the player playing first or second will win any combinatorial game just by looking at the initial state of the board.









## Game 0: Rook

Our first game is played on a chessboard, with a rook starting in the upper left corner. The players take turns moving the rook any number of spaces down or right (but not both, just like in Chess). Players are not allowed to move the rook up or left. Players can not count moving zero spaces as a move. If a player can't make any more moves, he loses (essentially, the player who moves the rook to the bottom right square wins).

<span><!--
unitsize(1cm);
for (real x = 0; x < 8; ++x) {
    for (real y = 0; y < 8; ++y) {
        if ((x+y)%2 == 0) {
            fill((x, y)--(x+1, y)--(x+1, y+1)--(x, y+1)--cycle, gray);
        }
        draw((x, y)--(x+1, y)--(x+1, y+1)--(x, y+1)--cycle, black+1);
    }
    label((string) x, (x+0.5, 8.5));
}
for (real y = 0; y < 8; ++y) {
    label((string) y, (-0.5, 7.5-y));
}
fill(circle((0.5, 7.5), 0.4), black);
--></span>

<img src="Game Theory Images/rook-board.svg" style="zoom:80%;" />

- It turns out that the winning strategy for this game is to keep the rook on the main diagonal (where $x=y$). If the first player moves $n$ spaces down, the second player should move $n$ spaces to the right (and vice versa) so that the rook is always on the main diagonal after the second player's turn. This means that the second player can always win this game. Make sure you understand why this works.
- We can classify game states into winning states and losing states.
  - A **winning state** (aka N-state, for Next player wins) is a state where the player who plays next can win. There must exist <u>at least one</u> move (the optimal strategy) to a losing state.
  - A **losing state** (aka P-state, for Previous player wins) is a state where the player who plays next cannot win. <u>All</u> the moves from a losing state result in winning states.
  - In this game, the losing states are the positions on the main diagonal, and the winning states are the positions outside the main diagonal.
  - We can calculate the winning and losing states by working backwards in the following process:
    1. The end state is a losing state (because the player who goes next is not the winner of the game).
    2. The other states in the 7th row or column ($(x,7)$ and $(7,x)$ for $0\le x \lt 7$) are winning states, because moving to $(7,7)$ results in a losing state.
    3. $(6, 6)$ is a losing state because both it's legal moves ($(6,7)$ and $(7,6)$) are winning states.
    4. The other states in the 6th row or column ($(x,6)$ and $(6,x)$ for $0\le x \lt 6$) are winning states because moving to $(6, 6)$ results in a losing state.
    5. $(5, 5)$ is a losing state because all it's legal moves are winning states ($(5,6)$, $(5, 7)$, $(6, 5)$, and $(7, 5)$).
    6. We can continue this process until we find that the starting state $(0, 0)$ is a losing state and thus the first player loses and the second player wins.
- Notice that all the losing states share the characteristic that $x-y=0$. It is a common pattern in Game Theory to find one simple condition to determine if a state is a losing state or a winning state. This condition often involves the parity (evenness/oddness) of some quantity. A good strategy is to play around with several of these quantities until 

## Game 1: Original Nim

The game of Nim was one of the first studied Game Theory games. A line of $n$ coins is placed on a table. Players take turns removing either $1$ or $2$ coins from the line. If there are no coins left for a player to take, they lose.

Here are some boards if you would like to play on paper:

<span><!--
unitsize(1cm);
// Typora mangles strings in quotes
// It should read {quote}{dollars}n=%d{dollars}{quote}
void drawRow(int n, real y, string l=format("$n=%dquot;, n)) {
    label(l, (-1.5, y));
    for (int x=0; x < n; ++x)
        fill(circle((x, y), 0.4), gray(.4));
}
int[] ns = {6, 8};
for (int i = 0; i < ns.length; ++i)
    drawRow(ns[i], -1.5*i);
drawRow(10, -1.5*ns.length, "$n=21quot;);
drawRow(10, -1.5*ns.length-1, "");
fill(circle((9.87, -1.5*ns.length-0.5), 0.4), gray(.4));
--></span>

![](Game Theory Images/nim-boards.svg)

Play the game a few times with a partner. Make sure you take turns playing first. Then answer the following questions:

1. Working backwards, determine which positions are winning states and losing states for $n=6$ and $n=8$.
2. Write a general rule to determine whether a state with $k$ coins is a winning state.
3. For a given value of $n$, how can you determine if the first or second player will win?
4. Briefly describe the optimal strategy.

5. What happens if the rules are changed such that the player who takes the last coin loses (the winning condition is negated)? Describe how to determine who will win this modified game.

## Game 2: 5-Nim

This game is the same as Original Nim, but you may take up to $5$ coins from the pile (no longer a line because it is too long).

<span><!--
unitsize(1cm);
// Typora mangles strings in quotes
// It should read {quote}{dollars}n=%d{dollars}{quote}
void drawRow(int n, real y, string l=format("$n=%dquot;, n)) {
    label(l, (-1.5, y));
    for (int x=0; x < n; ++x)
        fill(circle((x, y), 0.4), gray(.4));
}
drawRow(10, 0, "$n=40quot;);
drawRow(10, -1, "");
drawRow(10, -2, "");
drawRow(10, -3, "");
--></span>

![](Game Theory Images/nim-board-40.svg)

This time, try to guess the strategy before playing the game. Play the game once and see if your strategy holds. Then answer the following questions:

1. Write a general rule to determine whether a state with $k$ coins is a winning state.
2. For a given value of $n$, how can you determine if the first or second player will win?
3. Briefly describe the optimal strategy.





## Game 3: Pawns

This game is played on a row of $k$ boxes, with $2n$ pawns starting in the left-most box. Players alternate moving one pawn any number of steps to the right. If a pawn is in the right-most box, it can not be further moved. If a player can not make any further moves, they lose.

<span><!--
unitsize(2cm);
for (real x = 0; x < 5; ++x)
    draw((x, 0)--(x+1, 0)--(x+1, 1)--(x, 1)--cycle, black+1);
void triangle(real x, real y) {
    fill((x, y)--(x+0.2, y)--(x+0.1, y+0.3)--cycle, black);
}
for (real x = 0.1; x < 1; x += 0.5)
    for (real y = 0.1; y < 1; y += 0.5)
        triangle(x, y);
// Typora mangles strings in quotes
// It should read {quote}{dollars}n=2{dollars}{quote}
label("$n=2$", (-0.5, 0.65));
label("$k=5$", (-0.5, 0.35));
label("Goal", (4.5, 0.15));
--></span>

![](Game Theory Images/pawns-board.svg)

Play the game a few times with a partner. Make sure you take turns playing first. Then answer the following questions:

1. Working backwards, determine which positions are winning states and losing states for $n=2$ and $k=5$.
2. Write a general rule to determine whether a state is a winning state, for any value of $n$ and $k$.
3. Can you determine if the first or second player will win?
4. Briefly describe the optimal strategy.
5. How is the game of Pawns (with $n=1$ and $k=8$) related to the game of Rooks? Can you form a bijection between the states of the two games?
6. What happens when there are an odd number of pawns (say, $2n+1$)?

## AMC Game Theory Problem

Bela and Jenn play the following game on the closed interval $[0, n]$ of the real number line, where $n$ is a fixed integer greater than $4$. They take turns playing, with Bela going first. At his first turn, Bela chooses any real number in the interval $[0, n]$. Thereafter, the player whose turn it is chooses a real number that is more than one unit away from all numbers previously chosen by either player. A player unable to choose such a number loses. Using optimal strategy, which player will win the game? *(Source: 2020 10B #16)*

$\textbf{(A)} \text{ Bela will always win.}$
$\textbf{(B)} \text{ Jenn will always win.}$
$\textbf{(C)} \text{ Bela will win if and only if }n \text{ is odd.}$
$\textbf{(D)} \text{ Jenn will win if and only if }n \text{ is odd.}$
$\textbf{(E)} \text { Jenn will win if and only if } n>8.$

What is the optimal strategy in this problem?

Barbara and Jenna play the following game, in which they take turns. A number of coins lie on a table. When it is Barbara’s turn, she must remove $2$ or $4$ coins, unless only one coin remains, in which case she loses her turn. When it is Jenna’s turn, she must remove $1$ or $3$ coins. A coin flip determines who goes first. Whoever removes the last coin wins the game. Assume both players use their best strategy. Who will win when the game starts with $2013$ coins and when the game starts with $2014$ coins? *(Source: 2013 12B #18)*

$\textbf{(A)}$ Barbara will win with $2013$ coins and Jenna will win with $2014$ coins.
$\textbf{(B)}$ Barbara will win with $2013$ coins and whoever goes first will win with $2014$ coins.
$\textbf{(C)}$ Barbara will win with $2013$ coins and whoever goes second will win with $2014$ coins.
$\textbf{(D)}$ Jenna will win with $2013$ coins and Barbara will win with $2014$ coins.
$\textbf{(E)}$ Whoever goes first will win with $2013$ coins and and whoever goes second will win with $2014$ coins.