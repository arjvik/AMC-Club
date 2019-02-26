# Week 3: Sequences and Series

Sequences and series show up constantly throughout math. You encounter them in many different disciplines, from algebra to combinatorics. Today, we will talk about them and how we can leverage them to solve problems. 

## Arithmetic Sequences

An arithmetic sequence is a sequence where the difference between terms is constant. The following are all arithmetic sequences
$$
1 ,\  2 ,\  3 ,\  4 ,\  5 ,\  \cdots\\
5 ,\  7 ,\  9 ,\  11,\  13,\  \cdots\\
4 ,\  1 ,\  -2,\  -5,\  -8,\  \cdots\\
3 ,\  3+\pi,\ 3+2\pi ,\  3+3\pi ,\  3+4\pi ,\ \cdots\\
$$
The general form of an arithmetic sequence is:
$$
a ,\  a+d ,\  a+2d ,\  a+3d ,\  a+4d ,\  \cdots
$$

$a$ is the first term of the sequence.

$d$ is the common difference between terms.



Using this, lets try to write a general formula for the $n$th term of the sequence, $a_n$. Try to do this on your own before reading the solution.





The formula is:
$$
a_n = a + (n-1)d
$$
Notice the $n-1$ instead of $n$. The reason for this is that every time we move from one term to the next, we add $d$, but going from term $a_1$ to term $a_n$ only requires moving from term to term $n$ times. Make sure you understand why this is true.

### Quick check

**1. ** Mr. Newton's Calculus class is so hard that a constant number of students fail each week. But that's okay, since his class has expanded to a few thousand students. 

On the first week of school, he had 2019 students in his class. By the second week, only 2011 students were left. By the third week, only 2003 students were left.

**A.** Write out the first few terms of the sequence. Is this arithmetic? How do we know?

**B.** Find a formula for the number of students in his class in the $n$th week.

**C.** How many students will be left in his class in $12$ weeks?

**D.** In how many days will his class be empty?















### Solutions

**Problem 1.**

**A.** The first few times of the sequence are
$$
2019,\ 2011,\ 2003,\ 1995,\ 1987,\ 1979,\ \cdots.
$$
We know this is arithmetic because the difference between terms is constant.



**B.**  Using the formula we found earlier, we can find the formula to be
$$
a_n = 2019 - 8(n-1).
$$
**C.** Using the formula found in part B, we see
$$
a_{12} = 2019 - 8(12-1) = 2019 - 88 = \boxed{1931}
$$
**D.** We are trying to find the first day $n$ such that $a_n \le 0$. We can set up and solve an equation as follows.
$$
\begin{align}
a_n = 2019 - 8(n-1) &\le0 \\
2019 &\le 8(n-1) \\
\frac{2019}8 &\le n-1 \\
253 &\le n-1 \\
\boxed{254} &\le n
\end{align}
$$

## Sums of Arithmetic Sequences

To find the sum of an arithmetic sequence, we have to turn to a bit of clever thinking.

Imagine the following sequence, which we are trying to sum.
$$
S=1+2+3+4+5+6+7+8+9
$$
We notice that if we add the first and last terms together, or the second and second-to-last terms together, or any other opposite pair of terms, we get the same number, $10$. This motivates us to try the following:
$$
\begin{align}
2S
&= 1+2+3+4+5+6+7+8+9 \\
&+ 9+8+7+6+5+4+3+2+1 \\\hline
&=10+10+10+10+10+10+10+10+10 \\
&= 90 \\
S &= \boxed{45}
\end{align}
$$
Basically, we notice that the sum of the first and last terms is equal to the sum of any other opposite pair of terms. So multiplying the number of terms by the sum of the first and last terms gives us twice the original sum. Now, we can divide this by two to get the correct sum.

This gives us the following formula:
$$
a_1+a_2 + \cdots +a_n = \boxed{n\left(\frac{a_1+a_n}2\right)}
$$
A better way of remembering this is to take the average of the first and last term, and multiply it by the number of terms. This results in the same formula we see above.

### Quick Check

**2.** Tarun has been saving up to buy a new Ti-89 calculator. Every week, he gets an increasing amount of allowance from his parents. The first week of the year, he got $\$10$ from his parents. The second week, he got $\$15$.

**A.** Write a formula for the amount of money Tarun gets on the $n$th week (not the sum, just the actual amount he gets that week).

**B.** Write a formula for the total amount of money Tarun has at the end of each week.

**C.** How much money will Tarun have in $7$ weeks?

**D.** In how many weeks will he be able to buy the calculator if it costs $\$600$?















**3.** Without using the formula we derived earlier, write a new formula for the sum of an arithmetic sequence using only the variables $a$, $d$, and $n$. You may not have any $a_n$ terms in your formula. Here is a hint:
$$
a_1 + a_2 + \cdots + a_n = a + (a+d) + (a+2d) + (a+3d) + \cdots (a+(n-1)d)
$$
Try to separate the $a$ terms and the $d$ terms. How many of each will there be?













### Solutions

**Problem 2.**

**A.** Using what we learned in the previous section, we can write the formula as (with a little bit of simplification)

$a_n = 10 + 5(n-1) = 5+5n$

**B.** Our first term is $a_1=10$. Our last term is $a_n=5+5n$, as seen in the previous problem. Now, plugging in to our sum equation, we get
$$
a_1+a_2+\cdots+a_n = n\cdot\frac{15+5n}2 = \boxed{\frac{5n^2+15n}2}
$$
**C.** We plug in $7$ to the previous equation, and get
$$
a_1+a_2+\cdots+a_7 = 7\cdot\frac{15+35}2 = 7\cdot25 = \boxed{\$175}
$$
**D.** Similarly to last question, we set up an inequality and solve it. We wish to find the first $n$ such that the sum of the first $n$ terms of our sequence is at least $600$.
$$
\begin{align}
\frac{5n^2+15n}2 &\ge 600 \\
5n^2 + 15n &\ge 1200 \\
5n^2 + 15n - 1200 &\ge 0 \\
n^2 + 3n - 240 &\ge 0 \\
n &\ge 14.064... \\
n &\gt \boxed{15}
\end{align}
$$
So our answer is $15$ weeks.



**Problem 3.**

Separating the terms, we see that there are $n$ $a$s. Counting the $b$s is a little more complicated.