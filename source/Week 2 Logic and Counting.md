# Week 2: Logic and Counting

## Copyright Arjun Vikram and Aneesh Sharma, 2019

![Comic](https://lh4.googleusercontent.com/NKSdyot1OfRDManfWcSGuklNH2HfOYmQJKCBvRkNyRDJXeWhqCivCIFPxXoGR8NmmENG2-jiHMNuo1Oc_nOLUPuZw_w21bkj3g1fc5FTs-rVvXFfFHemEZdV-k_tf_T1deDsELyb)



## Logic

Logic problems test your logical reasoning. These are a favorite of the MAA, and at least a few questions each year will be purely logical reasoning. To solve logic problems, you just need to be organized and careful. 

If you are stumped, try making some guesses, and then check if those guesses work. If after making a guess, you reach a dead end where it is impossible to do anything, you know your guess was wrong. Then just try making another guess, and keep on repeating until you find your answer.

On problems relating to formal logic, i.e. what you learned in Geometry, think about the exact statements that each question and answer is making. Remember that the contrapositive of any statement is always true, but not necessarily the inverse or converse.

### Problems

1. Adrianna claims Bethany is lying. Bethany claims Crista is lying. Crista claims Bethany is lying. Daphne claims Adrianna is lying. Elizabeth claims that based on this information, she knows exactly how many other girls (not including herself) are lying. Based on what you see here, how many girls out of all 5 are lying? *(Source: Mock AMC 10 by AoPS, #13)*
   $$
   \textbf{(A)} \quad 1 \qquad
   \textbf{(B)} \quad 2 \qquad
   \textbf{(C)} \quad 3 \qquad
   \textbf{(D)} \quad 4 \qquad
   \textbf{(E)} \quad \text{Not enough information available}
   $$






2. What is the largest number of points a circle and triangle could possibly intersect at? *(Source: myself)*

$$
\textbf{(A)} \quad 0 \qquad
\textbf{(B)} \quad 2 \qquad
\textbf{(C)} \quad 3 \qquad
\textbf{(D)} \quad 4 \qquad
\textbf{(E)} \quad 6
$$





3. Ms. Carroll promised that anyone who got all the multiple choice questions right on the upcoming exam would receive an A on the exam. Which one of these statements necessarily follows logically? *(Source: 2017 AMC 10A #6)*

$\qquad\textbf{(A)}\ \text{If Lewis did not receive an A, then he got all of the multiple choice questions wrong.}\\$
$\qquad\textbf{(B)}\ \text{If Lewis did not receive an A, then he got at least one of the multiple choice questions wrong.}\\$
$\qquad\textbf{(C)}\ \text{If Lewis got at least one of the multiple choice questions wrong, then he did not receive an A.}\\$
$\qquad\textbf{(D)}\ \text{If Lewis received an A, then he got all of the multiple choice questions right.}\\$
$\qquad\textbf{(E)}\ \text{If Lewis received an A, then he got at least one of the multiple choice questions right.}$





4. What is the number of lowercase letters in the incorrect answers to this question? (Do not include the letter of the answer choice or any hyphens). *(Source: Mock AMC 10 by AoPS, #7)*
   $$
   \textbf{(A)} \quad \text{eleven} \qquad
   \textbf{(B)} \quad \text{twenty-two} \qquad
   \textbf{(C)} \quad \text{thirty-three} \qquad\\
   \textbf{(D)} \quad \text{forty-four} \qquad
   \textbf{(E)} \quad \text{fifty-five}
   $$







5. The numbers from $1$ to $16$ can be entered into a $4\times4$ grid so that the sum of the numbers in each of the four rows, four columns, and two diagonals are ten consecutive numbers in some order. The diagram shows a partially completed $4\times4$ grid. When completed, what number will go in the position marked by the $\star$ ? *(Source: Mock AMC 10 by AoPS, #17)*
   $$
   \begin{bmatrix}
   &&*&14\\
   &9&3&7\\
   &12&13&5\\
   10&11&6&4
   \end{bmatrix}
   $$

   $$
   \textbf{(A)} \quad 1 \qquad
   \textbf{(B)} \quad 2 \qquad
   \textbf{(C)} \quad 8 \qquad
   \textbf{(D)} \quad 15 \qquad
   \textbf{(E)} \quad 16
   $$















### Solutions

1. First of all, notice that all the names start with the letters A, B, C, D, and E. AMC always does this, to make it easier on you. Now we consider two cases, either A is lying or she is not.
   1. If A is lying, then B is telling the truth, then C is lying, then D is telling the truth.
   2. If A is telling the truth, then B is lying, then C is telling the truth, then D is lying.

   Either way, E knows that exactly two people other then her are lying, so she is telling the truth. Thus, exactly $\boxed{\textbf{(B)}\ 2}$ people are lying.

2. Drawing a diagram, we see that $\boxed{\textbf{(E)}\ 6}$ intersection points is possible.
   ![Circle and Triangle](https://i.ibb.co/s9MXKPb/circtri.png)
   
3. Let $p$ be getting all the multiple choice questions correct, and $q$ be getting an A on the test. The teacher said that $p \implies q$. We know that the contrapositive of this statement is true as well, so $\lnot q \implies \lnot p$. Thus, if he did not get an A on the test, he did not get all of the multiple choice questions correct (he got at least one wrong). As such, the answer is $\boxed{\textbf{(B)}}$.

4. After some trial and error, we see that if the answer is $\boxed{ \textbf {(C)}\ \text{thirty-three}}$, there are exactly 33 letters in the other answer choices.

5. Computing the sum of rows, columns, and diagonals that we already know, we get that the last row sums to $31$, the last column sums to $30$, and the diagonal sums to $39$. This means that the consecutive sums are $30\cdots39$. After some trial and error, we see that the following grid works, meaning the answer is $\boxed{\textbf{(D)}\ 15}$
   $$
   \begin{bmatrix}
   8&1&\boxed{15}&14\\
   19&9&3&7\\
   2&12&13&5\\
   10&11&6&4
   \end{bmatrix}
   $$







## Counting: Newton's Apple Ice Cream shop

Counting may seem like something that is easy, but it can get extremely complicated. A lot of AMC problems are about counting certain permutations and combinations of items. We will begin our exploration of combinatorics, which is the field of mathematics dedicated to counting, by learning about some permutations and combinations.



### Permutations with repetition

Imagine you are at an ice cream store, and there are $n$ flavors of ice cream. You want a cone with $k$ scoops on it. *How many ways are there to create different $k$-scoop cones with $n$ flavors?*

First of all, we say that a cone with strawberry ice cream on top and chocolate ice cream on the bottom is different from one with chocolate ice cream on top and strawberry on the bottom. This may be debatable, but for the context of this lesson, it is the truth. This basically means that we must consider order when we are counting outcomes.

Here is how we can count this. There are exactly $n$ choices for our first scoop, since we can pick out of all of the flavors. Then there are exactly $n$ choices for our second scoop, and then $n$ choices for our third scoop, and so on so forth. Thus, the total number of possible cones is
$$
\underbrace{n\times n\times \cdots \times n}_{\text{$k$ times}} = n^k
$$
This means that if you have $n$ items, and you want to have $k$ of them, where the **order of the items matters,** and **repeats *are* allowed,** there are $\boxed{n^k}$ possible outcomes.

#### Simple example problems:

1. Mr. Newton has three ties. He can wear any one of them to school each day. How many different ways can he wear a tie for a school week ($5$ days)?
   Answer: 3 choices, 5 days, so $3^5=\boxed{243}$
2. Mr. Newton, tired of the same routine every day, decides to change up his freshman calculus class. Each day for the entire six weeks ($30$ school days), he will give his class anywhere from $0$ to $6$ "quick-quizzes." a) How many ways can he schedule this? b) Also, would this be a good idea?
   Answer: a) 7 options ($0$, $1$, $2$ ... $6$), 30 days so $\boxed{7^{30}}$ 
                  b) Yes, because more math is more fun!



### Permutations without repetition

Next, imagine that too many people ordered cones that are only chocolate and the store is starting to run out, so they say that you may not have more than one scoop of one flavor of ice cream. *Now how many ways are there to make a $k$-scoop ice cream cone from $n$ flavors?*

We need to rethink our approach a bit. For the first scoop, there are $n$ choices. But now, after we take one scoop of that flavor, we can no longer use it anymore. Thus, the number of options we have for the second scoop is $n-1$. Now, since we have chosen two flavors already, we only have $n-2$ flavors to choose for our third scoop. Continuing on, we see that there are
$$
\begin{align}
&\qquad n \times (n-1) \times (n-2) \times \cdots \times (n-k+1)\\\\


&= n \times (n-1) \times (n-2) \times \cdots \times (n-k+1) \times \frac{(n-k) \times (n-k-1) \times \cdots \times 2 \times 1}{(n-k) \times (n-k-1) \times \cdots \times 2 \times 1}\\\\

&= \frac{n \times (n-1) \times (n-2) \times \cdots \times (n-k+1) \times (n-k) \times (n-k-1) \times \cdots \times 2 \times 1}{(n-k) \times (n-k-1) \times \cdots \times 2 \times 1}\\\\

&= \frac{n!}{(n-k)!}
\end{align}
$$
total outcomes.

Make sure you see why this works. We denote this commonly as $n\ \textbf P\ k$, which stands for $n$ pick $k$. This means that if you have $n$ items, and you want to have $k$ of them, where the **order of the items matters,** and **repeats are *not* allowed,** there are $\boxed{n\ \textbf P\ k = \frac{n!}{(n-k)!}}$ possible outcomes.

#### Simple example problems:

1. Mr. Newton has $30$ students. He wants to pick four different students to solve the warm-up problems. How many ways can he do this?
   Answer: He wants to pick 4 students from all 30 students, so $30\ \textbf P\ 4 = \frac{30!}{26!} = 30\cdot29\cdot28\cdot27=\boxed{657720}$.
2. Mr. Newton has 8 questions in his test bank, and he needs to pick 3 for today's quiz. How many ways can he do this?
   Answer: $8\ \textbf P\ 3 = \frac{8!}{5!} = 8*7*6 = \boxed{336}$.



### Combinations without repetition

Now, we imagine that the ice cream shop is under new management, and they decide that cones are too expensive, and they will only serve ice cream in bowls. We will say that when a bowl has strawberry and chocolate ice cream, it is the **exact same** as a bowl with chocolate and strawberry. We will say that because you can easily move the ice cream scoops around in your bowl. Again, while this is debatable, for the purpose of this analogy, we will consider it to be true.

*How many $k$-scoop bowls can we make from $n$ flavors?*

We start by pretending that order matters for a bit. We already know that when the order of the scoops matter, we will get $n\ \textbf P\ k$ outcomes. Now, we need to figure out how to correct for the order.

A good trick when you are stuck is to play around a bit with some examples. Let our flavors be $A$, $B$, and $C$. We see that both $A,B,C$ and $C,B,A$ are the same when we are trying to count combinations, but different when we count permutations. In order to correct for this, we must figure out how many times we count this single case.

After some more experimentation, we see that we are counting the case $A, B, C$ as

1. $A, B, C$
2. $A, C, B$
3. $B, A, C$
4. $B, C, A$
5. $C, A, B$
6. $C, B, A$

The reason we count this case $6$ times is that there are $6$ ways to rearrange 3 different letters. So we can just divide out how many ways there are to rearrange $k$ letters, which is just $k!$. (If you don't see why there are $k!$ ways of rearranging $k$ elements, think of it as $k\ \textbf P\ k$.)

So now our answer is that there are $\dfrac{n\ \textbf P\ k}{k!} = \dfrac{n!}{k!\cdot(n-k)!}$ outcomes.

We denote this as $n\ \textbf C\ k$, or more commonly as $\dbinom nk$, which stands for $n$ pick $k$. This means that if you have $n$ items, and you want to have $k$ of them, where the **order of the items *does not matter*,** and **repeats are *not* allowed,** there are $\boxed{n\ \textbf C\ k = \frac{n!}{k!\cdot(n-k)!}}$ possible outcomes.

#### Simple example problems:

1. Mr. Newton needs to choose 4 students for the Math team. He has 30 interested students. How many ways are there for him to select these 4 students, if the order in which the students are selected is unimportant?
   Answer: $30\ \textbf C\ 4= \dfrac{30\cdot29\cdot28\cdot27}{4\cdot3\cdot2\cdot1}=\boxed{27405}$.
2. Mr. Newton has 6 different vegan sandwiches in his refrigerator. He wants to take three of them for lunch. How many ways can he choose three of the sandwiches?
   Answer: $6\ \textbf C\ 3 = \frac{6!}{3!3!} = \frac{720}{36} = \boxed{20}$.



### Advanced: Combinations with repetition

**We will probably not cover this in class for the sake of time, but feel free to read this and do these problems at home.**

Its 2050, and the robot apocalypse has come. Now, all jobs have been taken over by robots. The ice cream shop still uses bowls, so the order of scoops does not matter, but the robots predict the future and always have enough ice cream on hand, so you can have multiple scoops of the same flavor.

How many $k$-scoop bowls can we make with $n$ flavors?

We first think of how the robots would serve customers. Imagine the ice cream shop as being a long line of ice cream tubs. The robot starts from the left-most end. The robot can only do two things, move to the right, or add a scoop from the tub it is in front of.

Here is an example:

Let the flavors be $A, B, C, D, \text{ and } E$. Imagine I want a bowl with $B, B, D, E$. My instructions to the robot will be
$$
\underbrace {\small\text{(start)}} _\text{Robot starts at $A$} \quad
\underbrace {\rightarrow} _\text{Move to $B$} \quad
\underbrace {\ *\ } _\text{Take $B$} \quad
\underbrace {\ *\ } _\text{Take $B$} \quad
\underbrace {\rightarrow} _\text{Move to $C$} \quad
\underbrace {\rightarrow} _\text{Move to $D$} \quad
\underbrace {\ *\ } _\text{Take $D$} \quad
\underbrace {\rightarrow} _\text{Move to $E$} \quad
\underbrace {\ *\ } _\text{Take $E$} \quad
$$
We see that we can represent any possible combination of flavors like this, as a permutation of $n - 1$ arrows and $k$ stars. We can then count the possible combinations of bowls by just counting how many ways we can arrange $n-1$ arrows and $k$ stars, which is just $\boxed{\dbinom{n+k-1}{n-1} = \dbinom{n+k-1}{k}}$.

#### Simple example problems:

1. Mr. Newton has a bag of $100$ pieces of candy. Mr. Newton wants to give this candy out to all the $30$ students in his class, but Mr. Newton is also feeling slightly evil today. He decides that he is going to distribute the candy with absolutely no restrictions. He may choose to not give certain students candy, or he may choose to give all the candy to one student. The only rule is that he gives out all of his candy. How many ways can he do this?
   (Note: this is probably very badly worded, because unlike the problem  writers who work for MAA, I am not paid to write math problems. The gist of this problem is it wants you to choose $100$ students to receive candy, without caring about repeats.)
   Answer: $n=30$, $k=100$. So we are looking for $\dbinom{129}{29}$ or $\dbinom{129}{100}$.
2. Mr. Newton decides that he is going to randomly select $10$ students in the class of $30$ students to receive bonus points on their Calculus grade. He draws $10$ names out of a hat with replacement. If he draws a student more than once, he will keep increasing their grade each time. How many different groups of students can he draw?
    Answer: $n=30$, $k=10$. So we are looking for $\dbinom{39}{29}$ or $\dbinom{39}{10}$.



### Problems

1. The number of diagonals that can be drawn in a polygon of 100 sides is: *(Source: 1950 AHSME Problem 45)*
$$
\textbf{(A)} \quad 98 \qquad
\textbf{(B)} \quad 4850 \qquad
\textbf{(C)} \quad 4950 \qquad
\textbf{(D)} \quad 8800 \qquad
\textbf{(E)} \quad 9900 \qquad
$$











2. A fair die is rolled six times. The probability of rolling at least a five at least five times is *(Source 1974 AHSME Problem 24)*
   $$
   \textbf{(A)} \quad \frac{2}{729} \qquad
   \textbf{(B)} \quad \frac{3}{729} \qquad
   \textbf{(C)} \quad \frac{12}{729} \qquad
   \textbf{(D)} \quad \frac{13}{729} \qquad
   \textbf{(E)} \quad \text{None of these} \qquad
   $$
   **HINT:** Probability is just counting the number of cases that satisfy the condition, $N$, counting the number of total cases, $T$, then computing $\frac NT$.











3. Bob and Alice each have a bag that contains one ball of each of the colors blue, green, orange, red, and violet. Alice randomly selects one ball from her bag and puts it into Bob's bag. Bob then randomly selects one ball from his bag and puts it into Alice's bag. What is the probability that after this process the contents of the two bags are the same? *(Source: 2006 AMC 10B #17)*

   $$
   \textbf{(A)} \quad \frac{1}{10} \qquad
   \textbf{(B)} \quad \frac{1}{6} \qquad
   \textbf{(C)} \quad \frac{1}{5} \qquad
   \textbf{(D)} \quad \frac{1}{3} \qquad
   \textbf{(E)} \quad \frac{1}{2} \qquad
   $$










4. Assume every 7-digit whole number is  a possible telephone number except those that begin with $0$ or $1$. What fraction of telephone numbers begin with $9$ and end with $0$? *(Source: 1985 AHJSME #22)*

$$
\textbf{(A)} \quad \frac{1}{63} \qquad
\textbf{(B)} \quad \frac{1}{80} \qquad
\textbf{(C)} \quad \frac{1}{81} \qquad
\textbf{(D)} \quad \frac{1}{90} \qquad
\textbf{(E)} \quad \frac{1}{100} \qquad
$$









5. At one of George Washington's parties, each man shook hands with everyone except his spouse, and no handshakes took place between women. If 13 married couples attended, how many handshakes were there among these 26 people? *(Source: 1990 AHSME #16)*

   $$
   \textbf{(A)} \quad 78 \qquad
   \textbf{(B)} \quad 135 \qquad
   \textbf{(C)} \quad 234 \qquad
   \textbf{(D)} \quad 312 \qquad
   \textbf{(E)} \quad 325 \qquad
   $$









6. Pat is to select six cookies from a tray containing only chocolate chip, oatmeal, and peanut butter cookies. There are at least six of each of these three kinds of cookies on the tray. How many different assortments of six cookies can be selected? *(Source: 2003 AMC 10A Problem #21)*













### Solutions

1. Each diagonal has its two endpoints as vertices of the 100-gon. Each pair of vertices determines exactly one diagonal. Therefore the answer should be $\dbinom{100}2 = 4950$. However this also counts the $100$ sides of the polygon, so the actual answer is $4950-100=\boxed{\textbf{(B)}\ 4850}$.

2. The probability of rolling at least a five on any one roll is $ \dfrac{2}{6}=\dfrac{1}{3} $. If there are exactly $ 5 $ fives or sixes rolled, there are $ \dbinom{6}{5}=6 $ ways to pick which of the rolls are the fives and sixes, and so the probability in this case is $ 6\left(\dfrac{1}{3}\right)^5\left(\dfrac{2}{3}\right)=\dfrac{12}{729} $. If there are exactly $ 6 $ fives or sixes rolled, then there is only one way to pick which of the rolls are fives and sixes, so the probability in this case is $ \left(\dfrac{1}{3}\right)^6=\dfrac{1}{729} $.

   Therefore, the total probability is $ \dfrac{12}{729}+\dfrac{1}{729}=\boxed{\textbf{(D)}\ \dfrac{13}{729}}$.

3. Let Alice put a ball of color $C$ in Bob's bag. For both bags to have the same contents, Bob must select one of the 2 $C$-colored balls out of the 6 balls in his bag, meaning the answer is $\dfrac26=\boxed{\textbf{(D)}\ \dfrac13}$.

4. First, let's count the number of total telephone numbers. There are $8$ choices for the first digit, and $10$ for the remaining $6$ digits, so the total number of telephone numbers is $8\cdot10^6$. If we only look at telephone numbers that begin with $9$ and end with $0$, there is only $1$ choice for both the first and last digit, and $10$ for the other, so the number of telephone numbers fitting these conditions is $10^5$. Thus, our answer is $\dfrac{10^5}{8\cdot10^6} = \boxed{\textbf{(B)}\ \dfrac1{80}}$.

5. We first count the number of handshakes between men, which is $\dbinom{13}2 = 78 $, since for every combination of two people, there will be a handshake. Next, we count the number of handshakes between men and women, which is $13\cdot12= 156 $ (each man shakes hands with the 12 women he is not married to). Our answer is $78+156 = \boxed{\textbf{(C)}\ 234}$

6. Using the formula we derived earlier in the combinations with repetitions section, since $n=6$ and $k=3$, this is just $\dbinom82=\boxed{\textbf{(D)}\ 28}$.