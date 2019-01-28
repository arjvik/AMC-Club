# Week 2: Logic and Counting

![Comic](https://lh4.googleusercontent.com/NKSdyot1OfRDManfWcSGuklNH2HfOYmQJKCBvRkNyRDJXeWhqCivCIFPxXoGR8NmmENG2-jiHMNuo1Oc_nOLUPuZw_w21bkj3g1fc5FTs-rVvXFfFHemEZdV-k_tf_T1deDsELyb)



## Logic

Logic problems test your logical reasoning. These are a favorite of the MAA, and at least a few questions each year will be purely logical reasoning. To solve logic problems, you just need to be organized and careful. 

If you are stumped, try making some guesses, and then check if those guesses work. If after making a guess, you reach a dead end where it is impossible to do anything, you know your guess was wrong. Then just try making another guess, and keep on repeating until you find your answer.

On problems relating to formal logic, i.e. what you learned in Geometry, think about the exact statements that each question and answer is making. Remember that the contrapositive of any statement is always true, but not necessarily the inverse or converse.

### Problems

1. Adrianna claims Bethany is lying. Bethany claims Crista is lying. Crista claims Bethany is lying. Daphne claims Adrianna is lying. Elizabeth claims that based on this information, she knows exactly how many other girls (not including herself) are lying. Based on what you see here, how many girls out of all 5 are lying? *(Credit: Mock AMC 10 by AoPS, #13)*
   $$
   \textbf{(A)} \quad 1 \qquad
   \textbf{(B)} \quad 2 \qquad
   \textbf{(C)} \quad 3 \qquad
   \textbf{(D)} \quad 4 \qquad
   \textbf{(E)} \quad \text{Not enough information available}
   $$






2. What is the largest number of points a circle and triangle could possibly intersect at?

$$
\textbf{(A)} \quad 0 \qquad
\textbf{(B)} \quad 2 \qquad
\textbf{(C)} \quad 3 \qquad
\textbf{(D)} \quad 4 \qquad
\textbf{(E)} \quad 6
$$



3. Ms. Carroll promised that anyone who got all the multiple choice questions right on the upcoming exam would receive an A on the exam. Which one of these statements necessarily follows logically? *(Credit: 2017 AMC 10A #6)*
   $$\qquad\textbf{(A)}\ \text{If Lewis did not receive an A, then he got all of the multiple choice questions wrong.}\\\qquad\textbf{(B)}\ \text{If Lewis did not receive an A, then he got at least one of the multiple choice questions wrong.}\\\qquad\textbf{(C)}\ \text{If Lewis got at least one of the multiple choice questions wrong, then he did not receive an A.}\\\qquad\textbf{(D)}\ \text{If Lewis received an A, then he got all of the multiple choice questions right.}\\\qquad\textbf{(E)}\ \text{If Lewis received an A, then he got at least one of the multiple choice questions right.}​$$



4. What is the number of lowercase letters in the incorrect answers to this question? (Do not include the letter of the answer choice or any hyphens). *(Credit: Mock AMC 10 by AoPS, #7)*
   $$
   \textbf{(A)} \quad \text{eleven} \qquad
   \textbf{(B)} \quad \text{twenty-two} \qquad
   \textbf{(C)} \quad \text{thirty-three} \qquad
   \textbf{(D)} \quad \text{forty-four} \qquad
   \textbf{(E)} \quad \text{fifty-five}
   $$



5. The numbers from $1$ to $16$ can be entered into a $4\times4$ grid so that the sum of the numbers in each of the four rows, four columns, and two diagonals are ten consecutive numbers in some order. The diagram shows a partially completed $4\times4$ grid. When completed, what number will go in the position marked by the $\star$ ?
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

   Either way, E knows that exactly two people other then her are lying, so she is telling the truth. Thus, exactly $\boxed 2$ people are lying.

2. Drawing a diagram, we see that $\boxed6$ intersection points is possible.
   ![Circle and Triangle](https://i.ibb.co/s9MXKPb/circtri.png)
   
3. Let $p​$ be getting all the multiple choice questions correct, and $q​$ be getting an A on the test. The teacher said that $p \implies q​$. We know that the contrapositive of this statement is true as well, so $\lnot q \implies \lnot p​$. Thus, if he did not get an A on the test, he did not get all of the multiple choice questions correct (he got at least one wrong). As such, the answer is $\boxed B​$.

4. After some trial and error, we see that if the answer is $\boxed{ \textbf {(C)}\ \text{thirty-three}}$, there are exactly 33 letters in the other answer choices.

5. Computing the sum of rows, columns, and diagonals that we already know, we get that the last row sums to $31​$, the last column sums to $30​$, and the diagonal sums to $39​$. This means that the consecutive sums are $30\cdots39​$. After some trial and error, we see that the following grid works, meaning the answer is $\boxed{\textbf{(D)}\ 15}​$
   $$
   \begin{bmatrix}
   8&1&\boxed{15}&14\\
   19&9&3&7\\
   2&12&13&5\\
   10&11&6&4
   \end{bmatrix}
   $$

