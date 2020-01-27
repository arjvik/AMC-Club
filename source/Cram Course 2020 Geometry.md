# AMC Club Geometry Cram Course

### Arjun Vikram, 2019

<img src="http://chquotes.synthasite.com/resources/calv_test.gif" alt="Daily Comic" style="zoom:80%;" />

## 0. AMC Tips

#### Scoring:

- **+6** points for correct answers
- **+0** points incorrect answers
- **+1.5** points skipped questions

Only guess if you have eliminated a few answers. We recommend guessing if you have 2 answers left (or 3 and you are willing to take a risk/have a strong feeling).

#### Timing

It is important to pace yourself on the real test. If you feel yourself struggling and losing time on one problem, skip it and move on. Even experienced AMC test takers sometimes skip a problem in the 10-20 range because we can't think of the optimal way to solve it. Remember that you only have 75 minutes, so make the best use of your time.

#### Geometry Specific

**DRAW A DIAGRAM!** This can not be stressed enough. Often a big diagram on a seperate piece of paper is extremely useful. Don't try to squeeze a diagram onto the problem booklet.

## 1. Areas and Volume

#### Triangle Area Formula

$A,B,C$ represent the angles at points $A,B,C$ respectively. $a,b,c$ represent side lengths $\overline{BC},\overline{AC},\overline{AB}$ (across from angles $A,B,C$) respectively. $s=\frac{a+b+c}2$ represents the semiperimeter of the triangle. $R$ and $r$ represent the circumradius and inradius respectively.

- Standard formula (half times base times height): $K=\frac12 bh$
- SAS area: $K=\frac12ab\sin C$ (and cyclic permutations)
- Heron's formula: $K=\sqrt{s(s-a)(s-b)(s-c)}$
- Inradius formula: $K=r\cdot s$
- Circumradius formula: $K=\dfrac{abc}{4R}$
- Equilateral Triangle formula: $K=\frac{\sqrt3}4a^2$

#### Areas of Quadrilaterals and Hexagons

The area of a rhombus is the product of the diagonals divided by 2 ($K=\frac{d_1d_2}2$).

To find the area of a hexagon, split it into triangles. For the most part they will be equilateral if the hexagon is equilateral. The area of an equilateral hexagon is $K=\frac{3\sqrt3}2s^2$.

#### Shoelace Theorem

When finding the area of a set of coordinates of points (given in clockwise or counterclockwise order), make use of Shoelace Theorem to find the area of those points. Start by writing the points vertically, and **repeat the first point at the end.** Then multiply down diagonals (much like finding the determinant of a matrix). Sum up the vaues on each side, take the positive difference between the two sides, and divide this by 2. See the following example for the points $\{(2,3), (5,5), (8,3), (7,1), (2,3)\}$.

![](https://jrkoenig.com/res/6/a/simple-shape-area-calculation.svg)

#### Pick's Theorem

When finding the area of a figure on a plane of dots, use Pick's theorem. $B$ is the number of boundary points, or lattice points on the edge of the figure. $I$ is the number of interior points, or lattice points inside the figure.
$$
A=\frac{B}2+I-1
$$
<img src="https://latex.artofproblemsolving.com/b/4/a/b4acbe6d46fcbed26c9dd24437ae47fcf13f70bc.png" style="zoom:33%;" />
$$
A = \frac{13}2+3-1 = 8.5
$$

#### 3D Geometry

Please study these formulas on your own. They are straight from HS Geometry. Some important things to know are that the volume of a pyramid (including a cone) is one third the volume of a prism with the same base and height.

## 2. Law of Sines/Cosines

Used to solve for remaining parts of a triangle when given at least 3 pieces of information.

- (Extended) Law of Sines: $\dfrac{\sin A}a = \dfrac{\sin B}b = \dfrac{\sin C}c = \dfrac1{2R}$
- Law of Cosines: $c^2 = a^2+b^2-2ab\cos C$  (and cyclic variants)

## 3. Solving for quantities

A common technique is to assign a variable to a quantity, such as a side length or angle. Then relate that quantity to other known quantities using the theorems you already know.

Another common technique is to solve for a known quantity and express it in two different ways. If you know the value of one of the expressions you found, you can solve for any variables in the other expression.

#### Example: 2019 AMC 10B #8

The figure below shows a square and four equilateral triangles, with each triangle having a side lying on a side of the square, such that each triangle has side length $2$ and the third vertices of the triangles meet at the center of the square. The region inside the square but outside the triangles is shaded. What is the area of the shaded region?

$\textbf{(A) } 4 \qquad \textbf{(B) } 12 - 4\sqrt{3} \qquad \textbf{(C) } 3\sqrt{3}\qquad \textbf{(D) } 4\sqrt{3} \qquad \textbf{(E) } 16 - 4\sqrt{3}$

<img src="https://latex.artofproblemsolving.com/c/d/d/cdd3a7f0a4a7e0d25eb30b89d96ca4cd2e86dcb9.png" style="zoom: 33%;" />

We know the area of the 4 triangles combined are $4\sqrt3$. Thus we just need to find the area of the entire square and subtract $4\sqrt3$ from it. We let the side length of the square be $x$. Then the height of one of these equilateral triangles is $\frac x2$. We also know (by splitting the equilateral triangles into 30-60-90 triangles) that the height of this triangle is $\sqrt3$. Thus $\frac x2=\sqrt3 \implies x=2\sqrt3$ so the area of the square is $x^2=12$ and our answer is $\boxed{\text{(B)}~~12-4\sqrt3}$.

## 4. Similarity and Congruence theorems

#### Theorems

- Similarity: AA, ASA, SSS
- Congruence: SSS, SAA, ASA, **Not ASS**

**Make use of these theorems!**

Similar triangles are often used in geometry problems where there are many triangles. Parrallel lines (alternate interior angles) and shared angles between two triangles often signify that you will find similar triangles.



#### Example: 2007 AMC 10B #21 (similar problem appeared on 2017 exam)

Right $\triangle ABC$ has $AB=3, BC=4,$ and $AC=5.$ Square $XYZW$ is inscribed in $\triangle ABC$ with $X$ and $Y$ on $\overline{AC}, W$ on $\overline{AB},$ and $Z$ on $\overline{BC}.$ What is the side length of the square?

$\textbf{(A) } \frac{3}{2} \qquad\textbf{(B) } \frac{60}{37} \qquad\textbf{(C) } \frac{12}{7} \qquad\textbf{(D) } \frac{23}{13} \qquad\textbf{(E)} 2 $

<img src="https://wiki-images.artofproblemsolving.com//d/da/2007AMC10B21.png" alt="2007AMC10B21.png" style="zoom:80%;" />

Let $x$ be the side length. Note that $\triangle WBZ\sim \triangle ABC$ with a similarity ratio of $\frac x5$. With a bit of pythagorean theorem (or right triangle geometric means) we can find that the height of $\triangle ABC$ from $\overline{AC}$ is $\frac{12}5$. The height of $\triangle WBZ$ is then $\frac x5 \cdot \frac{12}5 = \frac{12x}{25}$. If we add this to the height of the square $x$, we see that we should get the height of $\triangle ABC$. Therefore, $x + \frac{12x}{25}=\frac{37x}{25}=\frac{12}5 \implies \boxed{\text{(B)}~~x=\frac{60}{37}}$

## 5. Circles

#### Circle Tangency

When given a circle problem, try to connect the centers of the circles to the points of tangency and make triangles. From there, try to find ways to construct the length of the radii of circles you do not know. You can often construct a 30-60-90, 45-45-90 or equilateral triangle somehow.

#### Example: 2016 10A #15

Seven cookies of radius $$1$$ inch are cut from a circle of cookie dough, as shown. Neighboring cookies are tangent, and all except the center cookie are tangent to the edge of the dough. The leftover scrap is reshaped to form another cookie of the same thickness. What is the radius in inches of the scrap cookie?

$\textbf{(A) } \sqrt{2} \qquad \textbf{(B) } 1.5 \qquad \textbf{(C) } \sqrt{\pi} \qquad \textbf{(D) } \sqrt{2\pi} \qquad \textbf{(E) } \pi$

<img src="https://latex.artofproblemsolving.com/c/c/a/cca00f7535d16d5f82c2832dbebe7bf865368fed.png" style="zoom:33%;" />

If we connect the centers to the points of tangency, we note that the diameter of the outer circle is three times the diameter of the inner circle, so the outer radius is $3$. The area of the scrap cookie is thus $9\pi-7\cdot1^2\pi = 2\pi$, so when made into a circle it will have a radius of $\boxed{\text{(A)}~~\sqrt2}$.



#### Power of a Point

Power of a point relates the lengths of intersecting secants in a circle.

![Image result for power of a point](https://wiki-images.artofproblemsolving.com//f/f4/Pop.PNG)

**Case 1 - Two Chords:** $AE \cdot EC = BE \cdot ED$.

**Case 2 - Secant and Tangent:** $AB^2 = BC\cdot BD$.

**Case 3 - Two Tangents:** $CB \cdot CA = CD \cdot CE$. (Note: use $CA$ and $CE$ instead of $BA$ and $DE$).

The power of this point is equal to the product of the two distances on a line to the circle. If there is only a single point on both the line and circle, treat it as a double root. Note that this power is also equal to $R^2-d^2$ where $d$ is the distance from the center.

#### Angles in a circle

Please look back at your geometry notes to find this

## 6. Triangle Centers and Properties

#### Triangle Centers

| Center       | Intersection of...      | Properties                                                   |
| ------------ | ----------------------- | ------------------------------------------------------------ |
| Circumcenter | Perpendicular Bisectors | - Equidistant from all vertices<br />- Center of the circumcircle<br />- Solve for $R$ using $K=\frac{abc}{4R}$ |
| Incenter     | Angle Bisectors         | - Equidistant from all edges<br />- Center of the incircle<br />- Solve for $r$ using $K=rs$ |
| Centroid     | Medians                 | - Center of mass of triangle<br />- Average of all coordinates on plane<br />- Divides medians into $2:1$ ratio |
| Orthocenter  | Altitudes               | - Really nothing                                             |







#### Angle Bisector Theorem

![Image result for angle bisector theorem](https://www.dummies.com/wp-content/uploads/261943.image0.jpg)

Angle bisector theorem states that the ratio of the length of the segments formed by intersecting an angle bisector with the opposite sides is equal to the ratio of the lengths of the adjacent sides.

#### Triangle Inequality

In a triangle, the sum of two sides must always be greater than the third side. In algebraic form this means
$$
a<b<c, ~~~~a+b>c \implies \exists\triangle (a,b,c)
$$

#### Pythagorean Theorem/Inequality

In a right triangle, we know $c^2 = a^2+b^2$.

In an obtuse triangle, $c^2>a^2+b^2$

In an acute triangle, $c^2<a^2+b^2$

These statements are "if and only if" statements, so their converses, inverses, and contrapositives are also true.

#### Pythagorean Triples to know

$(3,4,5)$, $(5,12,13)$, $(6,8,10)$, $(7,24,25)$, $(8, 15, 17)$, $(9,40,41)$, $(11,60,61)$.

# 7. Coordinate Bashing

One common way to solve a problem is to place it on a coordinate plane, and find equations for points and lines. Then you can make use of algebra to find unknown quantities. Utilize the distance formula and different forms of linear equations.

#### Example: 2016 AMC 10A #19

In rectangle $ABCD,$ $AB=6$ and $BC=3$. Point $E$ between $B$ and $C$, and point $F$ between $E$ and $C$ are such that $BE=EF=FC$. Segments $\overline{AE}$ and $\overline{AF}$ intersect $\overline{BD}$ at $P$ and $Q$, respectively. The ratio $BP:PQ:QD$ can be written as $r:s:t$ where the greatest common factor of $r,s,$ and $t$ is $1.$ What is $r+s+t$?

$\textbf{(A) } 7 \qquad \textbf{(B) } 9 \qquad \textbf{(C) } 12 \qquad \textbf{(D) } 15 \qquad \textbf{(E) } 20$

<img src="https://latex.artofproblemsolving.com/1/5/8/15893c761d311ed13254fdea73b5a3079e88884f.png" alt="[asy] size(6cm); pair D=(0,0), C=(6,0), B=(6,3), A=(0,3); draw(A--B--C--D--cycle); draw(B--D); draw(A--(6,2)); draw(A--(6,1)); label(&quot;$A$&quot;, A, dir(135)); label(&quot;$B$&quot;, B, dir(45)); label(&quot;$C$&quot;, C, dir(-45)); label(&quot;$D$&quot;, D, dir(-135)); label(&quot;$Q$&quot;, extension(A,(6,1),B,D),dir(-90)); label(&quot;$P$&quot;, extension(A,(6,2),B,D), dir(90)); label(&quot;$F$&quot;, (6,1), dir(0)); label(&quot;$E$&quot;, (6,2), dir(0)); [/asy]" style="zoom:50%;" />

If we place this rectangle on the coordinate plane such that $D=(0,0)$ and $B=(6,3)$, we can find equations of lines $AE$, $AF$, and $DB$ and intersect them to find $P$ and $Q$. The equation of line $AE$ is $y=3-\frac16x$. The equation of line $AF$ is $y=3-\frac13x$. The equation of line $BD$ is $y=\frac12x$. We can intersect these lines and make use of the distance formula to find our answer.

#### Transformations

Please study your geometry notes and know what each transformation does and how it affects points on the coordinate plane

- Reflection over $x$-axis: $(x,y) \to (x,-y)$
- Reflection over $y-axis$: $(x,y)\to(-x,y)$
- Reflection over $y=x$: $(x,y)\to(y,x)$
- Rotation $90^\circ$ clockwise: $(x,y)\to(y,-x)$
- Rotation $180^\circ$ clockwise: $(x,y) -> (-x,-y)$
- Rotation $270^\circ$ clockwise: $(x,y)\to(-y,x)$
- Translation: $(x,y)\to(x+h,y+k)$

## 8. Geometric Probability

#### Probabilistic Geometry Problems

The probability of selecting a point from a certain region out of all possible points in a second region is the ratio of the areas of the two regions. For instance:

#### Example: 2011 AMC 10B #16

A dart board is a regular octagon divided into regions as shown. Suppose that a dart thrown at the board is equally likely to land anywhere on the board. What is the probability that the dart lands within the center square?

<img src="https://latex.artofproblemsolving.com/6/8/1/68141b2184d1682ae8f8d03c273456191e2cb1bd.png" style="zoom:50%;" />

$\textbf{(A)}\ \frac{\sqrt{2} - 1}{2} \qquad\textbf{(B)}\ \frac{1}{4} \qquad\textbf{(C)}\ \frac{2 - \sqrt{2}}{2} \qquad\textbf{(D)}\ \frac{\sqrt{2}}{4} \qquad\textbf{(E)}\ 2 - \sqrt{2}$

We know that the probability of hitting the center square is just the ratio of the area of the center square to the area of the entire octagon.

Let the side length of the octagon be $1$ (without loss of generality, as this holds true for all sizes). Then the area of the center square is $1$ and the area of the entire octagon is $2+2\sqrt2$. Therefore our answer is $\dfrac{1}{2+2\sqrt2} = \boxed{\text{(A)}~~\dfrac{\sqrt2-1}2}$

#### Applying Geometry to Probability Questions

Some questions aren't stated in terms of geometry, but we can make them geometry questions. The general gist is to place the problem on a coordinate plane, and then find the ratio of the area of the 

#### Example: 2017 AMC 10A #15

Chloe chooses a real number uniformly at random from the interval $[0, 2017]$. Independently, Laurent chooses a real number uniformly at random from the interval $[0, 4034]$. What is the probability that Laurent's number is greater than Chloe's number?

$\mathrm{\textbf{(A)} \ }\frac{1}{2}\qquad \mathrm{\textbf{(B)} \ } \frac{2}{3}\qquad \mathrm{\textbf{(C)} \ } \frac{3}{4}\qquad \mathrm{\textbf{(D)} \ } \frac{5}{6}\qquad \mathrm{\textbf{(E)} \ }\frac{7}{8}$

Let the $x$ axis represent Chloe's number and the $y$ axis represent Laurent's number.

<img src="https://i.ibb.co/3F0gnYt/screenshot.png" style="zoom:50%;" />

The shaded area represents the region where $y>x$. This region clearly contains $\frac34$ths of the area of the entire rectangle, therefore our answer is $\boxed{\text{(C)}~~\frac34}$.