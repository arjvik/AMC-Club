# AMC Club Combinatorics Cram Course

### Arjun Vikram and Maanas Sharma, 2019

## 1. Laws of Counting

- **Law of Addition:** If you have two or more events that are mutually *exclusive*, the number of outcomes is the number of outcomes of each event added together.
  - **Example:** If you have $12$ pairs of jeans and $4$ pairs of shorts, the number of ways to select a bottom to wear is $12+4=16$.
- **Law of Multiplication:** If you have two or more events that are mutually *independent*, the number of outcomes is the number of outcomes of each event multiplied together.
  - **Example:** If you have $6$ pairs of pants and $8$ pairs of shirts, the number of ways to select a pant and a shirt (independently) is $6\cdot8=48$.

Using these two laws to count the number of possible outcomes is known as **Constructive Counting**.

If there are two possible directions you could go when constructing a final outcome, you make use of casework to split them into two (or more) different cases. Once you have found an answer for each case, use the Law of Addition to combine the answers of each case into a final answer. Don't be afraid to have sub-cases in each case, but don't allow yourself to get too deep in sub-cases either.

## 2. One-to-One Correspondence

A **one-to-one correspondence** (aka bijection) is a mapping between two sets such that:
- each element of the first set is mapped to exactly one element of the second set, and
- each element of the second set is mapped from exactly one element of the first set.
- This means that the number of elements in both sets (or the cardinality) is the same.

We use one-to-one correspondences because they allow us to simplify counting problems by making a one-to-one correspondence from the set we wish to count elements of and a set which is easier to count elements of

For instance, the following are one-to-one correspondences:
- $\{1,2,3,4,5,6\} \longleftrightarrow \{1, 4, 9, 16, 25, 36\}$ (mapping function $f(x)=x^2$).
- $\{14,17,20,\cdots,50\} \longleftrightarrow \{1,2,3,\cdots,13\}$ (mapping function $f(x)=\dfrac{x-11}3$).
  - This exact idea is sometimes useful to count the number of terms in a sequence, where you know the first few terms and the last term. Find a mapping which makes the first term 1, the second term 2, the third term 3, and so on so forth. Then apply this mapping to the last term to find the number of terms.
- $\{\text{Su, M, T, W, Th, F, Sa}\} \longleftrightarrow \{1,2,3,4,5,6,7\}$ (mapping function outputs the position of the input).
- The set of all combinations with repetition of $k$ items from $n$ choices
      $\longleftrightarrow$ the set of all ways to permute $n-1$ stars and $k$ arrows on a line
      $\longleftrightarrow$ the set of all ways to select $k$ slots from $n+k-1$ slots.
  - We know that the cardinality of the last set is just $\dbinom{n+k-1}k$, so the number of combinations with repetition of is that value. See section 2.2 for more details.

## 3. Permutations and Combinations

Permutations means the order of the items matter, combinations means the order of the items does not matter.

|                     | Permutations | Combinations |
| ------------------- | ------------ | ------------ |
| **No Repetition**   | $n~\textbf P~k = \dfrac{n!}{(n-k)!}$<br />Spoken as $n$ Pick $k$ | $n~\textbf C~k = \dbinom nk = \dfrac{n!}{k!(n-k)!}$<br />Spoken as $n$ Choose $k$ |
| **With Repetition** | $n^k$ | $\dbinom{n+k-1}k=\dbinom{n+k-1}{n-1}$<br />My notation (not real): $n~{}^{\textbf C}_{\textbf R}~k$ |

### Examples:

- Mr. Newton has 8 questions in his test bank, and he needs to pick 3 for today's quiz. How many ways can he do this?
  Answer: $8\ \textbf P\ 3 = \frac{8!}{5!} = 8*7*6 = \boxed{336}$. We use permutations with no repetition because order matters and the same question can not appear twice.

- Mr. Newton has 6 different vegan sandwiches in his refrigerator. He wants to take three of them for lunch. How many ways can he choose three of the sandwiches?
  Answer: $6\ \textbf C\ 3 = \frac{6!}{3!3!} = \frac{720}{36} = \boxed{20}$. We use combinations for this with no repetition because the order of the sandwiches does not matter but the same sandwich can not appear twice.

### 3.2 Combinations With Repetition

The formula for choosing $k$ items out of $n$ where repeats are allowed is ${\dbinom{n+k-1}{n-1} = \dbinom{n+k-1}{k}}$ possible arrangements. We derive it using the following clever analogy. For more information, see [Lesson 2 Notes](https://sem-amc-club.tk/Week2.pdf).

For the purposes of our analogy, we are trying to count the number of ways to create ice cream bowls of $k$ scoops from $n$ different flavors, where order of the scoops does not matter, but the same flavor can be repeated. To begin thinking about our analogy, we pretend that the ice cream bowls are being constructed by robots.

We first think of how the robots would serve customers. Imagine the ice cream shop as being a long line of ice cream tubs. The robot starts from the left-most end. The robot can only do two things, move to the right, or add a scoop from the tub it is in front of.

Here is an example: Let the flavors be $A, B, C, D, \text{ and } E$. Imagine I want a bowl with $B, B, D, E$. My instructions to the robot will be

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
We see that we can represent any possible combination of flavors like this, as a permutation of $n - 1$ arrows and $k$ stars. This means that we can make a one-to-one correspondence between the set of all possible ice cream bowls and the set of all permutations of $n-1$ arrows and $k$ stars. In order to find the number of these permutations, we think about how we construct such a permutation. We can first fill in the $k$ stars, then fill in the remaining $n-1$ spaces with arrows. Therefore, we can make another one-to-one correspondence between the set of all permutations of $n-1$ arrows and $k$ stars and the set of all combinations of $k$ spaces out of $n+k-1$ spaces.

We can then count the possible combinations of bowls by just counting how many ways we can select $k$ spaces out of $n+k-1$ spaces, which is $\boxed{\dbinom{n+k-1}{k}}$.

This argument is sometimes called Stars and Bars, where the arrows are replaced with bars.

## 4. Complementary Counting

One common and powerful method of counting is **Complementary Counting**. When a problem asks to count the outcomes satisfying a difficult conditions, it is sometimes easier to count the outcomes that do NOT satisfy the condition and subtract that from the total number of possible outcomes.
$$
\#(\text{satisfying}) = \#(\text{total}) - \#(\text{not satisfying})
$$
For instance, if you are trying to count the number of positive integers less than or equal to 100 which are **not** divisible by either 3 or 7, you could first count the number of positive integers which *are* divisible by 3 or 7 (using PIE, see section 5), and then subtract that from 100 to find your answer.

## 5. Principle of Inclusion and Exclusion

PIE allows you to find the number of elements in the union of two sets. PIE says that
$$
|A \cup B| = |A| + |B| - |A \cap B|,
$$
where $|S|$ represents the cardinality (number of elements) of set $S$, $A \cup B$ represents the union of sets $A$ and $B$, and $A \cap B$ represents the intersection of sets $A$ and $B$.

<img src="https://lh5.googleusercontent.com/9FNSdwmQ0QuveCX-n1M-JR94hBqOV4nunAxXC-ww3T70ynql7PBcxR-Lw0a2kgYWjccCSWO1vSCUz51Lwvm6aT7qs6uaWdsAM9SFFuf5QHC2ZSLy19mPjTviORbSOBOrtajprwEb" alt="img" style="zoom: 100%;" />

PIE allows us to find the number of elements which satisfy at least one of two conditions.

PIE can be extended to three sets as follows:
$$
|A\cup B\cup C| = |A| + |B| + |C| - |A\cap B| - |A\cap C| - |B\cap C| + |A\cap B\cap C|
$$
<img src="https://lh3.googleusercontent.com/nULuXMsNcnVFjxxp2aywBbdsn9xYZt5tOfQpk1gWKi2jt20Q4YqgctzM9z9WH64jfKmMX1OoLngpbxK-RUcdnhhE-cd0vDYt6Wf7xnTDkWKtBghpa3G5h4b96u4togBBjNPYrj1m" alt="img" style="zoom:80%;" />

PIE can also be used to find the number of elements in at least two sets. To do this, be careful about what you are adding and subtracting, and add coefficients where needed.
$$
|(A\cap B)\cup(A\cap C)\cup(B\cap C)| = |A\cap B| + |A\cap C| + |B\cap C| - 2|A\cap B\cap C|
$$
We derive this by looking at a Venn diagram. Note that when we add all three of the two-set intersections, we count the middle region 3 times. Then, we just subtract away the middle region twice. We can also derive this by plugging in the sets $(A\cup B)$, $(A\cup C)$, and $(B\cap C)$ into our original PIE equation for two sets, and noticing that $(A\cap B)\cap(B\cap C)=A\cap B\cap C$ (and other similar permutations of this pattern).

PIE does not neccessarily have to be used only to find the number of elements of a set, it can also be applied in other scenarios, such as finding the sum of all integers in a set. In addition, PIE can be applied to probability.

**Example:** What is the sum of all integers from 1 to 100 that are multiples of 2 or 3?

The sum of all integers 1 to 100 which are multiples of 2 is $50\cdot\frac{102}2=2550$ (this is an arithmetic sequence with 50 terms and a mean of 51). The sum of all integers 1 to 100 which are multiples of 3 is similarly $33\cdot\frac{102}2=1683$. Finally, the sum of all integers 1 to 100 which are multiples of 6 is $16\cdot\frac{102}2=816$. Therefore, our answer is $2550+1683-816=\boxed{3417}$.

## 6. Probability

The probability of an event is the chance of that event happening, possibly given that some other conditions are true. There are two different ways to calculate probability, combinatorial and constructive.

**Combinatorial probability** uses the fact that
$$
P(\text{event}) = \dfrac{\#(\text{satisfying})}{\#(\text{total})}.
$$
To find $P(event)$ using combinatorial probability, simply use your existing combinatorial methods to find $\#(\text{satisfying})$ and $\#(\text{total})$. In most problems, $\#(\text{total})$ is usually the easiest to solve for, and you only need to use combinatorial tricks to find $\#(\text{satisfying})$. You can also use complimentary counting here and find $\#(\text{not satisfying})$ instead.

<u>You should be using combinatorial probability in most AMC problems</u>, simply because there are many more combinatorial tricks than probability tricks that you can use.

**Example:** find the probability of flipping at least 2 heads if you flip 3 coins.

There are $4$ ways to flip at least 2 heads, $HHH$, $HHT$, $HTH$, and $THH$. There are a total of $2^3=8$ different possible outcomes. Therefore, the probability is $\frac48=\boxed{\tfrac12}$

**Constructive probability** uses the Law of Addition and Law of Multiplication (their equivalents in probability) to construct the probability based on the choices made in the process.

Constructive probability is useful in specific places, such as recursive probability.

**Example:** find the probability of flipping at least 2 heads if you flip 3 coins.

There are two cases, based on the first coin flip:

Case 1 - first flip is $H$ (with chance $\frac12$): If the next flip is a $H$ (with chance $\frac12$), the results of the third flip do not matter. Otherwise, if the next flip is $T$ (with chance $\frac12$), the third flip must be $H$ (with chance $\frac12$). The probability of this ($HTH$) happening is $\frac12\cdot\frac12=\frac14$. Thus, the total probability of this case happening is $\frac12 \cdot \left(\frac12+\frac14\right)=\frac38$

Case 2 - first flip is $T$ (with chance $\frac12$): The next two flips must be $H$, which happens with chance $\frac14$, so the total probability of this case happening is $\frac12\cdot\frac14=\frac18$.

Therefore, our answer is $\frac38+\frac18=\boxed{\tfrac12}$.

## 7. Expected Value

The expected value of a number is the weighted average value of all the outcomes based on their probabilities. For instance, if you flip a coin 10 times, the expected value of the number of heads is 5, and if you roll a dice, the expected value of the roll is 3.5. The expected value of the sum of two variables is the sum of the expected value of those two variables.

## 8. Binomial Theorem

Binomial Theorem states that
$$
\begin{align*}
(a+b)^n &= \sum_{i=0}^n \binom ni a^ib^{n-i} \\
		&= \binom n0 a^n + \binom n1 a^{n-1}b + \binom n2 a^{n-2}b^2 + \cdots + \binom n n b^n \\
		&= a^n + na^{n-1}b+\tfrac{n(n-1)}2a^{n-2}b^2 + \cdots + nab^{n-1} + b^n
 \end{align*}
$$
Essentially, the number of $a^ib^{n-i}$ terms in the unsimplified expansion of $(a+b)^n$ is $\binom ni$, because to construct a term, you must select either $a$ or $b$ in each successive multiplication, and you must select exactly $i$ of the $a$ terms and $n-i$ of the $b$ terms.

**Example:** Find the sum
$$
\sum_{i=0}^n\binom ni=\binom n0+\binom n1+\binom n2+\cdots+\binom nn
$$
We see that this looks very similar to the binomial expansion of $(a+b)^n$, except that the $a$ and $b$ terms are missing. We try to set $a=1$ and $b=1$ to set those equal. Thus, $(1+1)^n$ is the value we are looking for, so our answer is $2^n$.