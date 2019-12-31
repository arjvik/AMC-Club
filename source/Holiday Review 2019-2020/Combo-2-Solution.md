## My solution to 2003 AMC 10A #21

### Problem

Pat is to select six cookies from a tray containing only chocolate  chip, oatmeal, and peanut butter cookies. There are at least six of each of these three kinds of cookies on the tray. How many different  assortments of six cookies can be selected? 

[Official AoPS solution](https://artofproblemsolving.com/wiki/index.php/2003_AMC_10A_Problems/Problem_21)

---

While the casework solution presented in the AoPS problem link is valid, I offer this easier to perform solution using a trick we discussed in class.

Look back at the notes for when we derived the formula for combinations with repetition. If we remembered this formula, we could simply plug in $n=3$ and $k=6$ to get $\dbinom82=\boxed{28}$.

Let's pretend you didn't remember this formula. We will use the same trick, by making a one-is-to-one correspondence to an easier set. We pretend that Pat is a robot with three stacks of cookies in front of her, and she needs to start at the left stack and end at the right stack. That means she needs exactly two **move right** instructions (represented by an arrow). She also needs to select six cookies, so she needs exactly six **select cookie** instructions (represented by a star). Therefore, I claim that we can form a one-is-to-one correspondence between the ways Pat can select cookies and permutations of 6 stars and 2 arrows. Make sure you see why this is true.

$$
\Large
\underset{1~~}{\underline{~*~}~~}
\underset{2~~}{\underline{~*~}~~}
\underset{3~~}{\underline{\,\rarr\,}~~}
\underset{4~~}{\underline{~*~}~~}
\underset{5~~}{\underline{~*~}~~}
\underset{6~~}{\underline{~*~}~~}
\underset{7~~}{\underline{\,\rarr\,}~~}
\underset{8~~}{\underline{~*~}~~}
$$

Now we just need to count the number of ways to permute 6 stars and 2 arrows. We can again form a one-is-to-one correspondence with an easier to count set. We can approach this by looking at how we would (as humans) construct such a permutation. We would first draw 8 blank lines, then select 2 of them to draw arrows, then fill the remaining 6 with stars. Therefore, I claim that there is a one-is-to-one correspondence between the ways to permute 6 stars and 2 arrows and the ways to choose 2 slots out of 8. We know that the number of ways to choose 2 slots out of 8 is simply $8\text{ choose }2$ or $\binom82=\frac{8\cdot7}2=28$, therefore our answer is $\boxed{28}$. (If you instead selected the 6 star slots first before filling in the remaining 2 with arrows, you would get the same answer as $\binom82=\binom86$ - see [here](https://math.stackexchange.com/a/849760) for a few reasons)

**Note:** sometimes this idea is called "stars and bars," and the arrows are replaced with bars. This is mostly due to the rhyme in the name. In addition, sometimes classic "stars and bars" has a restriction that each type of element (cookie in this case) must be chosen at least once. We can account for this in our robot analogy by assuming that the user has already selected $k$ cookies (one of each type) and only needs to select $n-k$ more before applying our trick (therefore getting an answer of $\binom{n-1}k$.