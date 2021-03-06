# Week 3: Sequences and Series

#### Arjun Vikram and Aneesh Sharma, February 2019

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









#### Quick Check

**1. ** Mr. Newton's Calculus class is so hard that a constant number of students fail and drop out each week. But that's okay, since his class has expanded to a few thousand students. On the first week of school, he had 2019 students in his class. By the second week, only 2011 students were left. By the third week, only 2003 students were left.

**A.** Write out the first few terms of the sequence. Is this arithmetic? How do we know?







**B.** Find a formula for the number of students in his class in the $n$th week.







**C.** How many students will be left in his class in $12$ weeks?







**D.** In how many days will his class be empty?































#### Solutions

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





#### Quick Check

**2.** Tarun has been saving up to buy a new Ti-89 calculator. Every week, he gets an increasing amount of allowance from his parents. The first week of the year, he got $\$10$ from his parents. The second week, he got $\$15​$.

**A.** Write a formula for the amount of money Tarun gets on the $n$th week (not the sum, just the actual amount he gets that week).



**B.** Write a formula for the total amount of money Tarun has at the end of each week.



**C.** How much money will Tarun have in $7$ weeks?



**D.** In how many weeks will he be able to buy the calculator if it costs $\$600$?







**3.** Without using the formula we derived earlier, write a new formula for the sum of an arithmetic sequence using only the variables $a$, $d$, and $n$. You may not have any $a_n$ terms in your formula. Once you do this, see if you can manipulate the new formula to find the original formula we found earlier.

Here is a hint:
$$
a_1 + a_2 + \cdots + a_n = a + (a+d) + (a+2d) + (a+3d) + \cdots (a+(n-1)d)
$$
Try to separate the $a$ terms and the $d$ terms. How many of each will there be? 









#### Solutions

**Problem 2.**

**A.** Using what we learned in the previous section, we can write the formula as (with a little bit of simplification)

$$
a_n = 10 + 5(n-1) = 5+5n
$$

**B.** Our first term is $a_1=10$. Our last term is $a_n=5+5n$, as seen in the previous problem. Now, plugging in to our sum equation, we get
$$
a_1+a_2+\cdots+a_n = n\cdot\frac{15+5n}2 = \boxed{\frac{5n^2+15n}2}.
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

Separating the terms, we see that there are $n$ $a$s. Counting the $d$s is a little more complicated. We notice that the first term has $0$ $d$s, the second has $1$ $d$, the third has $2$ $d$s, and the $n$th has $n-1$ $d$s. So all in all, there are $\dfrac{n(n-1)}2$ $d$ terms. So our answer is
$$
a_1+a_2+\cdots+a_n = \boxed{an + \frac{nd(n-1)}2}.
$$

We can manipulate the formula as follows:
$$
\begin{align}
an + \frac{nd(n-1)}2
&= \frac{2an + nd(n-1)}2\\
&= n\left(\frac{2a + (n-1)d}2\right)\\
&= n\left(\frac{a + (a+(n-1)d)}2\right)\\
&= n\left(\frac{a_1 + a_n}2\right).\\
\end{align}
$$


## Sigma Notation

When mathematicians wish to denote sums, they often use sigma notation, which uses the capital Greek letter $\Sigma$.

Here is a quick primer on sigma notation:
$$
\begin{align}
 \sum_{n=1}^{10}\ \ \ n &= 1+2+3+4+\cdots+10 \\
 \sum_{a=4}^{13}\ 2a &= 8+10+12+\cdots + 26 \\
 \sum_{x=a}^b\ f(x) &= f(a) + f(a+1) + \cdots + f(b)
 \end{align}
$$
We use similar notation for products, but instead with a $\Pi$, which is the capital pi symbol.
$$
\prod_{x=a}^b\ f(x) = f(a) \times f(a+1) \times \cdots \times f(b)
$$

#### Quick Check

**4.** What is the value of
$$
\sum_{n=2}^4 n^3+n^2+n
$$






**5.** Find (without just evaluating by hand!)
$$
\sum_{k=4}^{103} 2k-7
$$








#### Solutions

**Problem 4**

We just need to evaluate this by hand:
$$
\sum_{n=2}^4 n^3+n^2+n = 2^3+2^2+2^1+3^3+3^2+3^1+4^3+4^2+4^1 = 137.
$$
For those curious, there are a few neat formulas to compute the sum of the first $x$ numbers, squares, and cubes:
$$
\begin{align}
\sum_{n=1}^x\ n\  &= \frac{n(n+1)}2 \\
\sum_{n=1}^x\ n^2 &= \frac{n(n+1)(2n+1)}6 \\
\sum_{n=1}^x\ n^3 &= \left(\frac{n(n+1)}2\right)^2 \\
\end{align}
$$
As an added challenge, try evaluating this sum using the previous properties in the space below.





 



**Problem 5**

First, we need to make a substitution such that our sum starts at $n=1$, so we can apply our arithmetic sequence formula. We let $n=k-3$, so our sum becomes
$$
\sum_{n=1}^{100} 2(n+3) -7 = \sum_{n=1}^{100} 2n -1 = \sum_{n=1}^{100} 2(n-1)+1
$$
Now we see that we just have an arithmetic sequence with $a=1$, $d=2$ and $n=100$. The sum of this is just
$$
\sum_{n=1}^{100} 2(n-1)+1 = 100\cdot\frac{1+199}2 = \boxed{10,000}
$$











## Geometric Sequences

Just like arithmetic sequences have common differences, geometric sequences have common ratios between consecutive terms. The following are examples of geometric sequences:
$$
1 ,\  2 ,\  4 ,\  8 ,\  16 ,\  \cdots\\
2 ,\  6 ,\  18 ,\  54,\  162,\  \cdots\\
\frac12 ,\  \frac14 ,\ \frac18,\  \frac1{16},\  \frac1{32},\  \cdots\\
1 ,\ -2,\ 4,\ -8,\ 16,\ \cdots
$$
The general form of an arithmetic sequence is:
$$
a ,\  ar ,\  ar^2 ,\  ar^3 ,\  ar^4 ,\  \cdots
$$
$a$ is the first term.

$r$ is the common ratio.

Try to see if you can find the formula for the $n$th term of a geometric sequence on your own:



The formula is
$$
a_n = a\cdot r^{n-1}
$$
There is also a formula for the sum of the first $n​$ terms. The derivation is simple enough, and we may work through it on the board if there is time. If you are really curious, go to https://www.mathalino.com/reviewer/derivation-of-formulas/sum-of-finite-and-infinite-geometric-progression.

The formula is:
$$
\sum_{i=1}^n a\cdot r^{i-1} = a \cdot \frac{1-r^n}{1-r}.
$$
Geometric sequences also have another cool property: if $|r|<1$, we can find the sum of $\infty$ terms. We can do this as such: (we require a little bit of calculus to show this)
$$
\begin{align}
\sum_{i=1}^\infty a\cdot r^{i-1}
&= \lim_{x\to\infty}\sum_{i=1}^x a\cdot r^{i-1}\\
&= \lim_{x\to\infty}a \cdot \frac{1-r^n}{1-r}\\
&= \frac a{1-r}\lim_{x\to\infty}1-r^n\\
&= \frac a{1-r}\left(1-\lim_{x\to\infty}r^n\right)\\
&= \frac a{1-r}\left(1-0\right)\\
&= \frac a{1-r}.\\
\end{align}
$$

#### Quick Check

**6.** On Monday, John earns $\$1$. On Tuesday, he earns $\$0.50$. On Wednesday, he earns $\$0.25$. Each day afterwards, he earns half what he earned the previous day.

**A.** Write a formula for the amount of money he gets on the $n$th day.





**B.** How much money does he earn on the $6$th day? How much does he earn in total over the first $6$ days?







**C.** If this continues on forever, how much money will he make?



















#### Solutions

**Problem 6**

**A.** Using what we already know about geometric sequences, the formula is
$$
a_n = 1 \cdot \left(\frac12 \right)^{n-1} = 2^{-(n-1)}
$$
**B.** He will earn $2^{-5} = \frac1{32} = \$0.03125$ on the $6$th day. Plugging in this into our sum formula, he will have
$$
1\cdot\frac{1-(1/2)^n}{1-1/2} = \frac{1-1/64}{1/2} = \frac{63/64}{1/2} = \frac{63}{32} = \$1.96875.
$$


**C.** Plugging this into our formula for infinite sums, we get
$$
\frac{1}{1-1/2} = \frac1{1/2} = $2.
$$




## Problems

**1.** A grocer makes a display of cans in which the top row has one can and each lower row has two more cans than the row above it. If the display contains $100$ cans, how many rows does it contain? *(Source: 2004 AMC 12B)*

$\mathrm{(A)\ }5\qquad\mathrm{(B)\ }8\qquad\mathrm{(C)\ }9\qquad\mathrm{(D)\ }10\qquad\mathrm{(E)\ }11​$









**2.** How many non-similar triangles have angles whose degree measures are distinct positive integers in arithmetic progression? *(Source: 2006 AMC 10A)*

$\mathrm{(A) \ } 0\qquad\mathrm{(B) \ } 1\qquad\mathrm{(C) \ } 59\qquad\mathrm{(D) \ } 89\qquad\mathrm{(E) \ } 178\qquad$









**3.** Suppose that $\{a_n\}$ is an arithmetic sequence with $a_1+a_2+\cdots+a_{100}=100 \text{ and } a_{101}+a_{102}+\cdots+a_{200}=200.$What is the value of $a_2 - a_1 ?$ *(Source: 2002 AMC 10B)*

$\mathrm{(A) \ } 0.0001\qquad \mathrm{(B) \ } 0.001\qquad \mathrm{(C) \ } 0.01\qquad \mathrm{(D) \ } 0.1\qquad \mathrm{(E) \ } 1$







**4. **The first three terms of a geometric progression are $\sqrt3$, $\sqrt[3]3$, and $\sqrt[6]3$. What is the fourth term? *(Source: 2014 AMC 12A)*

$\textbf{(A) }1\qquad
\textbf{(B) }\sqrt[7]3\qquad
\textbf{(C) }\sqrt[8]3\qquad
\textbf{(D) }\sqrt[9]3\qquad
\textbf{(E) }\sqrt[10]3\qquad​$





**5. ** What is the average of $2012$ consecutive positive integers whose sum is $2012^3$? *(Source: Math League HS 2011-2012)*

 $\textbf{(A) }1\qquad
\textbf{(B) }2012\qquad
\textbf{(C) }4024\qquad
\textbf{(D) }2012^2\qquad
\textbf{(E) }2012^3\qquad​$





**6. ** In the pentagon $ABCDE$, the letters $A, B, C, D, E$ are replaced by the numbers $3, 5, 6, 7, 9$, although not necessarily in this order. The sums of the numbers at the ends of the line segments $AB, BC, CD, DE, EA$ form an arithmetic sequence, although not necessarily in that order. What is the middle term of the arithmetic sequence? *(Source: 2005 AMC 10A)*

$\mathrm{(A) \ } 9\qquad \mathrm{(B) \ } 10\qquad \mathrm{(C) \ } 11\qquad \mathrm{(D) \ } 12\qquad \mathrm{(E) \ } 13$



**Challenge Problems**

**7.** The terms of an arithmetic sequence add to $715$. The first term of the sequence is increased by $1$, the second term is increased by $3$, the third term is increased by $5$, and in general, the $k$th term is increased by the $k$th odd positive integer. The terms of the new sequence add to $836$. Find the sum of the first, last, and middle terms of the original sequence. *(Source: 2012 AIME 1)*







**8. **An infinite geometric series has sum 2005. A new series, obtained by squaring each term of the original series, has 10 times the sum of the original series. The common ratio of the original series is $\frac mn$ where $m$ and $n$ are relatively prime integers (basically, the fraction is in lowest terms). Find $m+n$. *(Source: 2005 AIME 2)*





























**Answers:** 1. D  2. C  3. C  4. A  5. D  6. D

**Challenge Problems:** 195 802