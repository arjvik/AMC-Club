## Supergames (Bonus!)

#### Arjun Vikram, SEM AMC Club

A supergame is a [combinatorial game](https://sem-amc-club.tk/GameTheory.pdf) made of the sum of smaller games, where a player can choose one game to make a move in on each turn. Players lose a supergame when they have no legal moves in any of the smaller games. In order to solve supergames like this, we must know whether each position has an even or odd number of potential moves, and whether the player who moves next can control that. We also need to know whether each game will end after finitely many turns, because if one game can be stalled infinitely, the supergame will too.

In order to solve supergames, we introduce the concept of a "nim value". We first define $\newcommand{\mex}{\operatorname{mex}}\mex(S)$ as the smallest nonnegative integer that does not appear in the set $S$ (e.g. $\mex(\{0,1,2,5,7\})=3$ and $\mex(\emptyset)=0$). We then define the nim value of a state as the $\mex$ of the set of nim values of all possible states that can be transitioned to. The nim value of a game that is over is defined as $0$ because the set of states that can be transitioned to is the empty set. We see that an N-state has a nonzero nim value and a P-state has a zero nim value.

> The following simple game serves to demonstrate nim values. Two players alternatively take turns removing one, two or three matches from a pile of matches. The player who removes the last match wins. Compute the nim value of all states and determine who wins.

We can iteratively calculate the nim values of each state, finding that the pattern is $\overline{0,1,2,3,\cdots}$.

<img src="../../AoPS-Notes/WOOT 2020/Notes/img/cc012fdfa78d5aa3cbc758140b9f8c0b24b4329c.png" alt="img" style="zoom:50%;" />

We see that the nim value is nonzero only when there is a zero position that can be reached, and it is zero only when no zero positions can be reached, meaning that N-states have nonzero nim values and P-states have zero nim values. This means that the first player wins if and only if the number of matches is not a multiple of 4.

> We then consider a supergame with two instances of this game. Let $G_1$ and $G_2$ be instances with the exact same number of initial matches. Which player has the winning strategy?
>
> <img src="../../AoPS-Notes/WOOT 2020/Notes/img/3eba4d9380c0a097402422861eb6880dedcd85f7.png" alt="img" style="zoom:50%;" />

We note that one winning strategy is for the second player to mirror the first player's moves exactly.

We can see that it doesn't actually matter whether or not $G_1$ and $G_2$ have the same number of initial matches, as long as their initial nim value is the same. Actually, the specific game played itself doesn't matter, as long as the two nim values are the same. Either way, if player one makes a move (wlog on game $G_1$) from a state with nim value of $n_1\ne0$ to a state with nim value $n_2<n_1$, player two can do the same on the other game (the $\mex$ definition of nim value means that you can make a move to *any* smaller value). If one player makes a move from a state with nim value of $n_1$ to a state with nim value of $n_2>n_1$, the second player can make a move from $n_2$ to $n_1$ again (this is different from our mirroring strategy because we are not guaranteed that the second game can also transition to a state with nim value $n_2$ as $n_2>n_1$). Ultimately, only the second player can reach a state where both nim values are zero (of which the final winning state is), so only he can possibly win (as long as neither game can stall endlessly).

> We then consider a supergame of two games of different nim values. For instance, let $G_1$ start with a nim value of $n_1$ and $G_2$ start with a nim value of $n_2$. WLOG, assume $n_1>n_2$.

Player one can reduce the nim value of $G_1$ to $n_2$, and then follow the above strategy (mirroring player two's moves when they reduce the nim sum and undoing them when they increase the nim sum) to win the game.

So now we see that player one wins a supergame of two games when $n_1\ne n_2$ and loses otherwise.

> How can we find the nim value of the supergame?

We can recursively define the nim value for all possible pairs of nim values of the smaller games. We start by noting that if $n_1=n_2$, the nim value is zero. We also note that if $n_1=0$ or $n_2=0$, the nim value of the supergame is the nim value of the non-zero game.

<img src="../../AoPS-Notes/WOOT 2020/Notes/img/3e6fc8a683526d6f51c50a38a72e3f534050efd7.png" alt="img" style="zoom:50%;" />

We can then use the $\mex$ definition to find the nim value when $n_1=1$ and $n_2=2$ is $\mex(\{0,1,2\})=3$. If we continue on similarly, we see that the resulting board appears to show that the nim value of the supergame is the XOR of the nim values of the smaller games.

<img src="../../AoPS-Notes/WOOT 2020/Notes/img/ee540b4ca403bc9c3cc07a39cb6d959ff74130c8.png" alt="img" style="zoom:50%;" />

Because XOR is commutative and associative, the nim value of the supergame of more than two smaller games is just the XOR of all the nim values. We can use this information to determine the winner of arbitrarily large supergames. The ideal strategy is still to bring the nim value of the supergame to zero and maintain it there.