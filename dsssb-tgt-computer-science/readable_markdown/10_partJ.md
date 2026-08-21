
---

# PART J - Mathematics, Statistics, Physics and Commerce for the Discipline Sections

> *The DSSSB Discipline papers mix in graduate-level Maths, Physics, Accounting and Economics. This Part covers only what actually appeared - not whole textbooks.*



## J1 Why This Part Exists



### J1.1 Read this before you panic


If you looked at the papers and saw questions on lasers, optical fibres, gross profit and differential equations, you were right to be surprised. These are not Computer Science topics.

DSSSB builds the "Discipline" question bank from the wider graduate syllabus of the subject stream, so Physics, Mathematics, Statistics, Accountancy and Business Economics questions appear alongside the computing ones. Counting across the three papers you shared, they make up roughly **15 to 25 questions**.


> **TIP: The right strategy for this Part**
>
> Do **not** try to master these subjects. You will lose weeks and gain little.
>
> Instead: learn the **specific formulas and definitions** in this Part. Nearly every non-CS question in those papers was a one-step application of a standard formula or a plain definition. Master these pages and you will convert most of those marks without opening a Physics textbook.
>
> If a question in the exam needs more than one step of unfamiliar mathematics, **skip it**. With negative marking, a skipped question costs you nothing; a guessed one costs 0.25.



## J2 Numerical Methods



### J2.1 Interpolation - the core idea


You know the value of a function at a few points. **Interpolation** estimates its value at a point **in between** those known points. **Extrapolation** estimates a value **outside** the known range and is much less reliable.

- **Interpolation** - Constructing new data points within the range of a discrete set of known data points. It is carried out using **curve fitting and linear analysis** - you fit a curve through the known points and read off the value you need.
- **Interpolant** - The function produced by interpolation.


> **NOTE: Direct PYQ**
>
> "Interpolation is carried out using data from:" Options: regression analysis / curve fitting and regression analysis / linear interpolation / **curve fitting and linear analysis**. Answer: **curve fitting and linear analysis**.
>
> The distinction that matters: **interpolation** passes *exactly through* every known data point, whereas **regression** finds a best-fit line that need not pass through any point. So options mentioning regression are wrong.



### J2.2 Types of interpolation



| Method | Description | Smoothness of the result |
|---|---|---|
| PIECEWISE CONSTANT (nearest neighbour) | Each interval simply takes the value of the nearest known point. The graph is a staircase | The LEAST smooth - it is discontinuous, giving the "softest"/crudest interpolant with no curvature |
| Linear | Straight lines joining consecutive points | Continuous but has sharp corners (kinks) at the data points |
| Polynomial | A single polynomial of degree n-1 through all n points | Smooth everywhere, but high-degree polynomials oscillate wildly near the edges (Runge's phenomenon) |
| SPLINE | Low-degree polynomials (usually cubic) on each interval, joined so that the first and second derivatives match | Smooth AND well behaved - the practical favourite |
| NONLINEAR | Uses a nonlinear model. Used in PROBABILITY THEORY AND STATISTICS; the GAUSSIAN PROCESS is a classic EXAMPLE (also called kriging) | Depends on the model |



> **NOTE: Two direct PYQs on interpolation types**
>
> "Which method creates interpolants that are softer?" Answer key: **Piecewise constant interpolation**. The reasoning in the paper's sense is that piecewise constant interpolation makes no attempt at curvature - it produces the crudest, "softest" (least mathematically demanding) interpolant, a simple step function.
>
> "The ______ interpolation method is used in probability theory and statistics, and the Gaussian process is one example." Answer: **nonlinear**. The Gaussian process (kriging) is a nonlinear, probabilistic interpolation technique used heavily in statistics and machine learning. Linear, polynomial and spline interpolation are all deterministic curve-fitting techniques, not probabilistic ones.



### J2.3 Lagrange interpolation - solved



*Lagrange's interpolation formula*
```
For points (x0,y0), (x1,y1), ... (xn,yn):

  f(x) = SUM over i of  [ y_i x PRODUCT over j not equal to i of (x - x_j)/(x_i - x_j) ]

For THREE points it becomes:

  f(x) =  y0 (x-x1)(x-x2) / [(x0-x1)(x0-x2)]
        + y1 (x-x0)(x-x2) / [(x1-x0)(x1-x2)]
        + y2 (x-x0)(x-x1) / [(x2-x0)(x2-x1)]
```



> **NOTE: PYQ worked out**
>
> "The values of x are 1, 3, 4 and those of f(x) are 1, 27, 64. What is the polynomial equation by using the Lagrange interpolation formula?"
>
> Answer: **8x^2 - 19x + 12**
>
> Rather than expanding the whole Lagrange formula (slow and error-prone under exam pressure), use this **verification shortcut**: the correct polynomial must reproduce every given data point. Test each option.
>
> Test **8x^2 - 19x + 12**:
> At x = 1: 8(1) - 19(1) + 12 = 8 - 19 + 12 = **1** - matches f(1) = 1
> At x = 3: 8(9) - 19(3) + 12 = 72 - 57 + 12 = **27** - matches f(3) = 27
> At x = 4: 8(16) - 19(4) + 12 = 128 - 76 + 12 = **64** - matches f(4) = 64
> All three points match, so this is the answer.
>
> Test **8x^2 + 9x + 12** (a distractor):
> At x = 1: 8 + 9 + 12 = 29, but f(1) should be 1. Fails immediately.
>
> **Exam technique:** for any "find the interpolating polynomial" question, substitute the smallest given x into each option. Usually three of the four options fail on the first substitution.



### J2.4 Finite difference operators


These appear in numerical-methods questions and look intimidating, but only a few identities are ever asked.


| Operator | Symbol | Definition |
|---|---|---|
| Forward difference | Delta | Delta f(x) = f(x + h) - f(x) |
| Backward difference | nabla | nabla f(x) = f(x) - f(x - h) |
| Central difference | delta | delta f(x) = f(x + h/2) - f(x - h/2) |
| Averaging (mean) operator | mu | mu f(x) = [ f(x + h/2) + f(x - h/2) ] / 2 |
| Shift operator | E | E f(x) = f(x + h) |



#### The identities you should memorise


*Key operator relations*
```
Delta = E - 1                      so    E = 1 + Delta
nabla = 1 - E^(-1)
delta = E^(1/2) - E^(-1/2)
mu    = ( E^(1/2) + E^(-1/2) ) / 2

AND THE ONE THAT IS ASKED:
   mu^2 = 1 + delta^2 / 4  =  ( delta^2 + 4 ) / 4
```



> **NOTE: PYQ worked out - the averaging operator**
>
> "If mu is an averaging operator and delta^n is the nth central difference operator, then what is the value of mu^2?"
>
> Answer: **mu^2 = (1/4)(delta^2 + 4)**
>
> Derivation, so you can reconstruct it if you forget:
> mu = ( E^(1/2) + E^(-1/2) ) / 2
>
> Square both sides:
> mu^2 = ( E^(1/2) + E^(-1/2) )^2 / 4
> = ( E + 2 + E^(-1) ) / 4
>
> Now note that delta = E^(1/2) - E^(-1/2), so
> delta^2 = E - 2 + E^(-1),  which gives  E + E^(-1) = delta^2 + 2
>
> Substitute:
> mu^2 = ( delta^2 + 2 + 2 ) / 4 = ( delta^2 + 4 ) / 4 = **(1/4)(delta^2 + 4)**
>
> The wrong options change either the fraction (1/2 instead of 1/4) or the constant (6 or 8 instead of 4). Remember the pair of numbers: **one quarter, and plus four.**



> **NOTE: PYQ worked out - nth difference of an exponential**
>
> "What is the value of Delta^n e^(ax+b)?"
>
> Answer: **(e^(ah) - 1)^n e^(ax+b)**
>
> Work out the first difference, then spot the pattern:
> Delta e^(ax+b) = e^(a(x+h)+b) - e^(ax+b)
> = e^(ax+b) e^(ah) - e^(ax+b)
> = e^(ax+b) ( e^(ah) - 1 )
>
> So one application multiplies by the factor (e^(ah) - 1). Applying it n times multiplies by that factor n times:
> Delta^n e^(ax+b) = **(e^(ah) - 1)^n e^(ax+b)**
>
> The two things to check in the options: the sign inside the bracket must be **minus 1** (not plus 1), and the exponent must stay **ax + b** (not ax - b), because differencing never changes the constant b.



## J3 Probability and Statistics



### J3.1 Basic probability


- **Probability** - P(E) = (number of favourable outcomes) / (total number of equally likely outcomes). It always lies between 0 and 1.
- **Classical definition** - Attributed to **Pierre-Simon Laplace**, who formalised probability as the ratio of favourable to total equally likely cases.
- **Sample space** - The set of all possible outcomes.
- **Mutually exclusive events** - Cannot happen together, so P(A and B) = 0 and P(A or B) = P(A) + P(B).
- **Independent events** - One does not affect the other, so P(A and B) = P(A) x P(B).
- **Addition rule** - P(A or B) = P(A) + P(B) - P(A and B).
- **Conditional probability** - P(A given B) = P(A and B) / P(B).
- **Complement** - P(not A) = 1 - P(A).


> **NOTE: Direct PYQ**
>
> "Who invented the probability definition?" Options: **Simon Laplace**, Euclid, None, Einstein. Answer: **Simon Laplace** (Pierre-Simon Laplace). He gave the classical definition of probability in his 1812 work. Euclid is geometry; Einstein is physics.



### J3.2 Bayesian vs frequentist probability



| Approach | Interpretation of probability |
|---|---|
| Classical / Frequency probability | The long-run relative frequency of an event in repeated identical trials. Objective |
| BAYESIAN probability | Probability as a **DEGREE OF BELIEF** in a proposition, which is **updated as new evidence arrives**. It is a "probability calculus of views/beliefs that obeys particular rules" (the Cox axioms) |


- **Bayes' theorem** - P(A given B) = [ P(B given A) x P(A) ] / P(B). Here P(A) is the **prior**, P(A given B) is the **posterior**, and P(B given A) is the **likelihood**.


> **NOTE: Direct PYQ**
>
> "Which probability calculus of views obeys particular rules?" Options: Standard deviation, Variance, **Bayesian probability**, Frequency probability. Answer: **Bayesian probability**.
>
> The phrase "calculus of **views**" is the clue - Bayesian probability treats probability as a quantified *belief or opinion*, updated by evidence according to fixed rules. Standard deviation and variance are *measures of spread*, not interpretations of probability at all.



### J3.3 Solved probability problems from the papers



> **NOTE: PYQ worked out - two dice, sum neither 5 nor 9**
>
> "If two dice are thrown, find the probability that the sum is neither 5 nor 9."
>
> Answer: **7/9**
>
> Total outcomes when two dice are thrown = 6 x 6 = **36**.
>
> Count the ways to get a sum of **5**: (1,4), (2,3), (3,2), (4,1) = **4 ways**
> Count the ways to get a sum of **9**: (3,6), (4,5), (5,4), (6,3) = **4 ways**
>
> These two events cannot happen together, so the sum is 5 or 9 in 4 + 4 = **8** ways.
>
> P(sum is 5 or 9) = 8/36 = 2/9
>
> P(sum is NEITHER 5 nor 9) = 1 - 2/9 = **7/9**
>
> Technique: whenever a question says "**neither ... nor ...**" or "**not**", count the unwanted cases and subtract from 1. It is almost always faster than counting the wanted cases.



> **NOTE: PYQ worked out - even number on a die**
>
> "Suppose a six faced die is thrown. Then the probability that the number appearing on the top is even is equal to:"
>
> Answer: **1/2**
>
> Sample space = {1, 2, 3, 4, 5, 6}, so 6 outcomes.
> Even numbers = {2, 4, 6}, so 3 favourable outcomes.
> P(even) = 3/6 = **1/2**
>
> Note the distractors 1/4, 1/6 and 1/9. The value 1/6 is the probability of one *specific* number, which is a common misread.



### J3.4 Probability distributions



| Distribution | Discrete or continuous | Used for |
|---|---|---|
| Bernoulli | Discrete | A single trial with two outcomes (success/failure) |
| BINOMIAL | Discrete | The number of successes in n independent trials. Mean = np, Variance = npq |
| POISSON | DISCRETE | The number of RARE events in a fixed interval of time or space. Mean = Variance = lambda. THE generic probability function for discrete random variables in this context |
| Geometric | Discrete | Number of trials until the first success |
| Uniform | Either | All outcomes equally likely |
| NORMAL (GAUSSIAN) | CONTINUOUS | The bell curve. Symmetric about the mean; mean = median = mode |
| Exponential | Continuous | Time between events in a Poisson process |
| Rayleigh | Continuous | Magnitude of a two-dimensional vector; used in signal fading models |
| Chi-square | Continuous | Testing goodness of fit and INDEPENDENCE in contingency tables |
| t distribution | Continuous | Small-sample tests of means |
| F distribution | Continuous | Comparing variances (ANOVA) |
| Cumulative distribution | Either | F(x) = P(X <= x). It is a FUNCTION, not a distribution family in itself |



> **NOTE: PYQ worked out**
>
> "Identify the generic probability density function that corresponds with discrete random variables." Options: Cumulative distribution, Gaussian distribution, **Poisson distribution**, Rayleigh distribution. Answer: **Poisson distribution**.
>
> Reasoning: the question asks for the one associated with **DISCRETE** random variables. Gaussian (normal) and Rayleigh are both **continuous** distributions. "Cumulative distribution" is a general concept applying to both. Only **Poisson** is a discrete distribution among the options - it counts whole numbers of events (0, 1, 2, 3 ...).



### J3.5 Measures of central tendency and dispersion



| Measure | Definition |
|---|---|
| Arithmetic Mean (AM) | Sum of all values divided by the number of values. The most common average |
| Median | The middle value when data is arranged in order. The **second quartile (Q2)**. Unaffected by extreme values |
| Mode | The most frequently occurring value |
| Geometric Mean (GM) | The nth root of the product of n values. Used for growth rates and ratios |
| Harmonic Mean (HM) | n divided by the sum of the reciprocals. Used for averaging rates and speeds |
| Relation | AM >= GM >= HM always |
| Range | Maximum minus minimum |
| Quartiles | Q1, Q2 (median), Q3 divide the data into four parts |
| Variance | The mean of the squared deviations from the mean |
| Standard deviation | The square root of the variance. Same units as the data |
| Coefficient of variation | (Standard deviation / Mean) x 100 - a unit-free measure of relative spread |



> **NOTE: PYQ worked out - a classic property of the mean**
>
> "The algebraic sum of deviations is zero when measured from the ______." Options: second quartile, geometric mean, **arithmetic mean**, harmonic mean. Answer: **arithmetic mean**.
>
> Proof in one line. The sum of deviations from the mean is
> SUM (x_i - mean) = SUM x_i - n x mean
>
> But by definition mean = (SUM x_i) / n, so n x mean = SUM x_i. Substituting:
> SUM (x_i - mean) = SUM x_i - SUM x_i = **0**
>
> Verify with a tiny example: data 2, 4, 6. Mean = 4. Deviations are -2, 0, +2, which sum to 0.
>
> This is a **defining property of the arithmetic mean** and one of the most frequently asked statistics facts. Note the related property: the sum of *squared* deviations is **minimum** when measured from the arithmetic mean.



### J3.6 Chi-square test for independence


- **Purpose** - To test whether two categorical variables are **independent** (unassociated), using a contingency table.
- **Degrees of freedom** - For an r x c contingency table, **df = (r - 1)(c - 1)**.


> **NOTE: PYQ worked out**
>
> "Eighty eight residents of a city, who were interviewed in a city are classified as male or female and also as drinkers or non-drinkers of tea. For testing association between sex and drinking of tea, the test statistic follows:"
>
> Answer: **Chi square distribution with 1 degree of freedom**
>
> Reasoning:
> - Testing **association between two categorical variables** means a **chi-square test of independence**. That eliminates the t-distribution and normal-distribution options.
> - Now the degrees of freedom. The table has **2 rows** (male, female) and **2 columns** (drinker, non-drinker).
> df = (r - 1)(c - 1) = (2 - 1)(2 - 1) = 1 x 1 = **1**
>
> Note that the sample size (88) is a deliberate red herring - it does not enter the degrees-of-freedom calculation at all. The distractor "chi square with 2 degrees of freedom" is what you get if you mistakenly use (r + c - 2) or forget to subtract.



## J4 Series, Calculus, Matrices and Differential Equations



### J4.1 Convergence of a p-series


- **p-series** - A series of the form SUM 1/n^p.
- **Convergence rule** - The p-series **CONVERGES if p > 1** and **DIVERGES if p <= 1**.


> **NOTE: PYQ worked out**
>
> "The series SUM 1 / (n^2)^(1/5) is:" Answer: **convergent**.
>
> Simplify the general term first - this is the whole trick:
> 1 / (n^2)^(1/5) = 1 / n^(2/5)
>
> So this is a p-series with **p = 2/5 = 0.4**.
>
> Since p = 0.4 is **less than 1**, the strict p-series rule says this series **DIVERGES**. However, the official answer key for this paper marked it **convergent**.
>
> **How to handle this in the exam:** learn the rule properly - *p greater than 1 converges, p less than or equal to 1 diverges*. Recognise that this particular key appears to be in error (or the printed expression differed from what was intended, e.g. a fifth root of n^2 in the denominator raised differently). Do not let one questionable key entry undermine the rule, which is standard and will be needed for other questions.
>
> Quick reference: SUM 1/n diverges (harmonic series, p = 1). SUM 1/n^2 converges (p = 2). SUM 1/sqrt(n) diverges (p = 1/2).



### J4.2 Euler's theorem on homogeneous functions


- **Homogeneous function of degree n** - f(tx, ty) = t^n f(x, y).
- **Euler's theorem** - If f is homogeneous of degree n, then x (df/dx) + y (df/dy) = **n f**.


> **NOTE: PYQ worked out**
>
> "If u = tan inverse (y/x), then x (du/dx) + y (du/dy) = ?"
>
> Answer: **0**
>
> Method 1 - Euler's theorem (fast). Check the degree of homogeneity of u:
> u(tx, ty) = tan inverse ( ty / tx ) = tan inverse ( y / x ) = u(x, y) = t^0 u(x, y)
>
> So u is homogeneous of **degree 0**. By Euler's theorem:
> x (du/dx) + y (du/dy) = n u = **0** x u = **0**
>
> Method 2 - direct differentiation (to confirm). With u = arctan(y/x):
> du/dx = -y / (x^2 + y^2)
> du/dy =  x / (x^2 + y^2)
>
> So x (du/dx) + y (du/dy) = -xy/(x^2+y^2) + xy/(x^2+y^2) = **0**
>
> **Lesson worth remembering:** any function of the pure ratio y/x is homogeneous of degree zero, so this expression is always 0. Recognising that saves the whole calculation.



### J4.3 Vector calculus - the normal to a surface


- **Gradient** - For a surface F(x, y, z) = constant, the vector **grad F = (dF/dx, dF/dy, dF/dz)** is **normal (perpendicular)** to the surface at every point.
- **Unit normal** - grad F divided by its own magnitude.


> **NOTE: PYQ worked out**
>
> "Find a unit vector normal to the surface x^3 + y^3 + 3xyz = 3 at the point (1, 2, -1)."
>
> Answer: **(1/sqrt 14)( -i + 3j + 2k )**
>
> Step 1 - write F and take partial derivatives.
> F = x^3 + y^3 + 3xyz - 3
>
> dF/dx = 3x^2 + 3yz
> dF/dy = 3y^2 + 3xz
> dF/dz = 3xy
>
> Step 2 - evaluate at the point (1, 2, -1).
> dF/dx = 3(1)^2 + 3(2)(-1) = 3 - 6 = **-3**
> dF/dy = 3(2)^2 + 3(1)(-1) = 12 - 3 = **9**
> dF/dz = 3(1)(2) = **6**
>
> So grad F = -3i + 9j + 6k
>
> Step 3 - simplify by taking out the common factor 3.
> grad F = 3( -i + 3j + 2k )
>
> Step 4 - find the magnitude of the simplified direction vector.
> | -i + 3j + 2k | = sqrt( 1 + 9 + 4 ) = **sqrt 14**
>
> Step 5 - the unit normal.
> n = ( -i + 3j + 2k ) / **sqrt 14**
>
> Note the distractors: one option has the signs as (i - 3j + 2k) and another divides by sqrt 2 instead of sqrt 14. Always (a) take out the common factor before computing the magnitude, and (b) double-check every sign.



### J4.4 Volume of a tetrahedron



> **NOTE: PYQ worked out**
>
> "The volume of the tetrahedron bounded by the surfaces x = 0, y = 0, z = 0 and x/a + y/b + z/c = 1 is:"
>
> Answer: **abc / 6**
>
> This is a standard result worth memorising outright. The plane x/a + y/b + z/c = 1 cuts the three axes at (a,0,0), (0,b,0) and (0,0,c). Together with the three coordinate planes it forms a tetrahedron with three mutually perpendicular edges of lengths a, b and c.
>
> Volume of such a tetrahedron = (1/3) x (base area) x height
> = (1/3) x (1/2 x a x b) x c
> = **abc / 6**
>
> Memory hook: the box (cuboid) with sides a, b, c has volume abc; the corner tetrahedron is exactly **one sixth** of it.



### J4.5 Matrices


- **Characteristic equation** - For a matrix A, it is **det(A - lambda I) = 0**. Its roots are the **eigenvalues**.
- **For a 2x2 matrix** - The characteristic equation is **lambda^2 - (trace)lambda + (determinant) = 0**, where trace = sum of the diagonal elements.
- **Cayley-Hamilton theorem** - Every square matrix satisfies its own characteristic equation. This is the standard tool for computing high powers of a matrix.


> **NOTE: PYQ worked out - characteristic equation**
>
> "The characteristic equation of matrix A = [[1, 4], [3, 5]] is ______."
>
> Answer: **lambda^2 - 6 lambda - 7 = 0**
>
> Use the 2x2 shortcut. For A = [[a, b], [c, d]]:
> characteristic equation is  lambda^2 - (a + d) lambda + (ad - bc) = 0
>
> Here a = 1, b = 4, c = 3, d = 5.
> **Trace** = a + d = 1 + 5 = **6**
> **Determinant** = ad - bc = (1)(5) - (4)(3) = 5 - 12 = **-7**
>
> Substituting:
> lambda^2 - (6) lambda + (-7) = 0
> **lambda^2 - 6 lambda - 7 = 0**
>
> Note both signs carefully: the trace term is always **minus** trace, and here the determinant is itself negative, so it appears as **- 7**. The distractors flip these signs.



> **NOTE: PYQ worked out - high power of a matrix**
>
> "If A = [[1,0,0],[0,-1,0],[1,0,1]] then the matrix for A^6 is ______."
>
> Answer: **[[1,0,0],[0,1,0],[6,0,1]]**
>
> Rather than multiplying six times, compute A^2 and look for the pattern.
>
> A^2: multiply A by A. The structure is lower-triangular-ish with a simple pattern:
> - The (1,1) entry stays 1 (1 x 1 = 1).
> - The (2,2) entry is (-1) x (-1) = **+1**.
> - The (3,3) entry stays 1.
> - The (3,1) entry accumulates: in A it is 1; in A^2 it becomes 2.
>
> So A^2 = [[1,0,0],[0,1,0],[2,0,1]]
>
> The pattern is clear: **A^n has (3,1) entry = n, and the (2,2) entry is (-1)^n.**
>
> For n = 6 (an even power): (-1)^6 = **+1**, and the (3,1) entry = **6**.
>
> A^6 = **[[1,0,0],[0,1,0],[6,0,1]]**
>
> **Technique to carry into the exam:** for these "high power of a matrix" questions, compute A^2 (and A^3 if needed), spot the arithmetic pattern in the changing entries, then jump to the required power. Also use parity: an even power always makes a -1 diagonal entry become +1.



### J4.6 Differential equations


- **Order** - The highest derivative present.
- **Degree** - The power of the highest derivative.
- **General solution** - Contains arbitrary constants.
- **Particular solution** - The specific part corresponding to the right-hand side (also called the particular integral, PI).
- **Complementary function (CF)** - The solution of the homogeneous equation (right-hand side = 0).
- **Complete solution** - CF + PI.


#### Forming a differential equation from a solution

If a solution contains **n arbitrary constants**, the differential equation is of **order n**, and you eliminate the constants by differentiating n times.


> **NOTE: PYQ worked out**
>
> "Which of the following options is the differential equation corresponding to y = a e^(2x) + b e^(-x) where a and b are arbitrary?"
>
> Answer: **y'' - y' - 2y = 0**
>
> Fast method - work backwards from the exponents. A solution of the form
> y = a e^(m1 x) + b e^(m2 x)
> comes from a second-order equation whose **auxiliary equation** has roots m1 and m2.
>
> Here the roots are **m = 2** and **m = -1**.
>
> So the auxiliary equation is (m - 2)(m + 1) = 0, i.e.
> m^2 - m - 2 = 0
>
> Translate m^2 to y'', m to y', and the constant to y:
> **y'' - y' - 2y = 0**
>
> Verify quickly with y = e^(2x): y' = 2e^(2x), y'' = 4e^(2x).
> Then y'' - y' - 2y = 4e^(2x) - 2e^(2x) - 2e^(2x) = 0. Correct.
>
> **Technique:** read the exponents off the given solution, form (m - r1)(m - r2) = 0, expand, and replace powers of m with derivatives of y. This converts a two-minute elimination problem into a fifteen-second one.



> **NOTE: PYQ worked out - separable equation**
>
> "The general solution of dy/dx = e^(x + y) is:"
>
> Answer: **e^x + e^(-y) = c**
>
> Method - separate the variables.
> dy/dx = e^(x+y) = e^x . e^y          (splitting the exponential)
>
> Bring all y terms to one side and all x terms to the other:
> dy / e^y = e^x dx
> e^(-y) dy = e^x dx
>
> Integrate both sides:
> INTEGRAL e^(-y) dy = INTEGRAL e^x dx
> -e^(-y) = e^x + k
>
> Rearranging (and absorbing the constant):
> **e^x + e^(-y) = c**
>
> Check the signs in the options carefully - the distractors offer e^(-x) + e^y and similar sign swaps. The rule: integrating e^(-y) gives **minus** e^(-y), which is what flips the sign when you rearrange.



> **NOTE: PYQ worked out - particular solution with a repeated root**
>
> "Which of the following options is the particular solution of the differential equation y'' - 6y' + 9y = 2 e^(3t)?"
>
> Answer: **t^2 e^(3t)**
>
> Step 1 - find the auxiliary equation and its roots.
> m^2 - 6m + 9 = 0, which factorises as (m - 3)^2 = 0.
> So m = 3 is a **REPEATED (double) root**.
>
> Step 2 - recognise the resonance case.
> The right-hand side is 2e^(3t), and **3 is already a root of the auxiliary equation - twice**. This is the "resonance" or "failure case". The normal trial solution Ce^(3t) will not work, and neither will Cte^(3t).
>
> Step 3 - apply the rule for repeated roots.
> When the exponent matches a root of multiplicity k, multiply the trial solution by **t^k**. Here k = 2, so the particular integral has the form **C t^2 e^(3t)**.
>
> That matches the answer **t^2 e^(3t)**.
>
> **The rule to memorise:** for y'' + ay' + by = e^(rt),
> - if r is NOT a root, the PI is proportional to e^(rt)
> - if r is a SIMPLE root, the PI is proportional to t e^(rt)
> - if r is a DOUBLE root, the PI is proportional to t^2 e^(rt)
>
> The distractors e^(3t)/2, e^(3t) and e^(3t)/9 all ignore the repeated root - they are what you would wrongly get by naive substitution.



> **NOTE: PYQ worked out - operator form**
>
> "The particular solution of the differential equation (D^4 - 18D^2 + 81)y = ______"  Answer: **x^2 e^(3x)**
>
> Here D is the differential operator d/dx. Factorise the operator polynomial:
> D^4 - 18D^2 + 81 = (D^2 - 9)^2 = (D - 3)^2 (D + 3)^2
>
> So **m = 3 is a double root** (and so is m = -3). Exactly as in the previous question, an e^(3x) forcing term against a **double** root gives a particular solution containing **x^2 e^(3x)**.
>
> Notice this is the same underlying idea asked twice in two different papers with different notation (t versus x, D-operator versus primes). **Learn the resonance rule once and you gain both marks.**



## J5 Physics Topics That Appeared



### J5.1 Lasers


- **LASER** - **Light Amplification by Stimulated Emission of Radiation.**
- **Properties of laser light** - Monochromatic (single wavelength), coherent (waves in phase), highly directional, very intense.
- **Population inversion** - The condition where more atoms are in the excited state than the ground state. It is **essential** for laser action.
- **Pumping** - Supplying energy to achieve population inversion (optical, electrical, chemical).
- **Metastable state** - An excited state with an unusually long lifetime (about 10^-3 s instead of 10^-8 s), which allows population inversion to build up.


| Process | Description | Lifetime of the initial state |
|---|---|---|
| Stimulated ABSORPTION | An atom in the GROUND STATE absorbs a photon and jumps to an excited state | The ground state is the lowest energy state, so an atom can stay there FOREVER unless disturbed - its lifetime is INFINITE |
| Spontaneous emission | An excited atom drops to a lower state on its own, emitting a photon in a random direction and phase | About 10^-8 s for an ordinary excited state |
| Stimulated emission | An incoming photon triggers an excited atom to emit a second identical photon - same direction, phase and frequency. This is what AMPLIFIES the light | - |



> **NOTE: PYQ worked out**
>
> "What is the lifetime of an atom's ground state in Stimulated Absorption?" Options: 2 minutes, 11 hours, 5 seconds, **Infinity**. Answer: **Infinity**.
>
> Reasoning: "lifetime" means the average time an atom remains in a state before spontaneously leaving it. The **ground state is the lowest possible energy level** - there is nowhere lower for the atom to fall to. So without external excitation, an atom remains in the ground state indefinitely. Its lifetime is therefore taken as **infinite**. The numeric options are arbitrary distractors.



#### The CO2 laser

- **CO2 laser** - A molecular gas laser, one of the most powerful and efficient continuous-wave lasers. Emits in the infrared at **10.6 micrometres**. Used for cutting, welding and surgery.
- **Which transitions produce the output** - In atoms, laser transitions occur between **electronic** energy levels. But CO2 is a **molecule**, and molecules also have **vibrational** and **rotational** energy levels. The CO2 laser output comes from transitions between **VIBRATIONAL states** (specifically the asymmetric stretching mode dropping to the symmetric stretching mode).


> **NOTE: Direct PYQ**
>
> "Which transition generates laser output in CO2 molecule?" Options: **Vibrational states**, Pulsed output, Molecular states, Energy states. Answer: **Vibrational states**.
>
> Note the distractors: "pulsed output" describes a *mode of operation*, not a transition; "molecular states" and "energy states" are too vague to be the specific answer. The precise, examinable fact is that CO2 lasing occurs between **vibrational** energy levels of the molecule.



### J5.2 Polarisation and retardation plates


- **Polarisation** - A property of **TRANSVERSE waves** in which the oscillations occur in a particular direction perpendicular to the direction of propagation. Light and all electromagnetic waves are transverse, so they can be polarised. **Longitudinal waves such as sound CANNOT be polarised** - this is the standard proof that light is transverse.
- **Unpolarised light** - Vibrations in all directions perpendicular to propagation.
- **Plane / linearly polarised light** - Vibrations confined to one plane.
- **Polaroid** - A sheet that transmits only one plane of vibration. Its transmission direction is the **pass axis**.
- **Brewster's law** - At the Brewster angle, reflected light is completely plane polarised; tan(Brewster angle) = refractive index.
- **Malus's law** - Transmitted intensity I = I0 cos^2(theta), where theta is the angle between the polariser and analyser axes.


> **NOTE: PYQ worked out**
>
> "Does polarisation vary with direction?" Options: Polarising axis, **Transverse wave**, Propagating axis, Pass axis. Answer: **Transverse wave**.
>
> The question is oddly worded, but the concept being tested is fundamental: polarisation is a **direction-dependent** property, and it exists **only because light is a transverse wave**. Since the oscillation is perpendicular to the direction of travel, there is a *choice* of direction for the oscillation - and that choice is what polarisation describes. In a longitudinal wave the oscillation is always along the direction of travel, so there is no such choice and no polarisation.



#### Double refraction and retardation plates

- **Birefringence (double refraction)** - Certain crystals (calcite, quartz) have **two different refractive indices** depending on the direction of polarisation. An entering ray splits into two: the **ordinary (O) ray** and the **extraordinary (E) ray**, which travel at different speeds.
- **Retardation plate (wave plate)** - A thin slice of a birefringent crystal. Because the O and E rays travel at different speeds through it, one is **retarded** relative to the other, producing a **phase shift** between them. This phase shift is what the plate is for.
- **Quarter-wave plate** - Introduces a phase difference of 90 degrees (a quarter wavelength). Converts linear polarisation to circular.
- **Half-wave plate** - Introduces a phase difference of 180 degrees. Rotates the plane of linear polarisation.


> **NOTE: PYQ worked out**
>
> "Which phenomenon causes a phase shift in the retardation plates?" Options: Phasor plates, Retardation plates, Polaroid filters, **Double refraction**. Answer: **Double refraction**.
>
> The causal chain: the plate is made of a **birefringent (doubly refracting)** crystal, therefore the two polarisation components see different refractive indices, therefore they travel at different speeds, therefore they emerge with a **phase difference**. So the underlying *phenomenon* is **double refraction**.
>
> Note that "Retardation plates" is offered as an option - but that is the *device*, not the phenomenon, so it cannot be the answer to "which phenomenon". Watch for this device-versus-phenomenon trap.



### J5.3 LED and photon energy


- **Photon energy formula** - E = hc / lambda, where h = 6.626 x 10^-34 J s and c = 3 x 10^8 m/s.
- **The practical shortcut** - **E (in eV) = 12400 / lambda (in Angstrom)** - memorise this. Some books use 12375 or 12398; all give the same answer to two decimal places.
- **Band gap of an LED** - The photon emitted has energy approximately equal to the semiconductor's band gap Eg, so Eg = hc/lambda.


> **NOTE: PYQ worked out**
>
> "An LED emits green light of wavelength lambda = 5511.11 Angstrom. Find the value of Eg."
>
> Answer: **2.25 eV**
>
> Use the shortcut formula:
> Eg (eV) = 12400 / lambda (in Angstrom)
> = 12400 / 5511.11
> = **2.25 eV**
>
> Check by the long method if you prefer:
> lambda = 5511.11 Angstrom = 5511.11 x 10^-10 m
> E = hc / lambda = (6.626 x 10^-34 x 3 x 10^8) / (5511.11 x 10^-10)
> = (1.9878 x 10^-25) / (5.51111 x 10^-7)
> = 3.608 x 10^-19 J
>
> Convert to electron volts by dividing by 1.6 x 10^-19:
> E = 3.608 x 10^-19 / 1.6 x 10^-19 = **2.25 eV**
>
> Note the distractor **3.606 eV** - that is the answer in units of 10^-19 **joules** mistaken for eV. Always finish the conversion. Memorise **12400 / lambda(Angstrom) = energy in eV** and this becomes a ten-second question.



### J5.4 Simple harmonic motion - the spring problem


- **Time period of a spring-mass system** - T = 2 pi sqrt( m / k ), where k is the spring constant.
- **Static extension** - When a mass m hangs at rest, the spring stretches by x where kx = mg, so **x = mg / k**.
- **The useful combination** - From T = 2 pi sqrt(m/k) we get m/k = T^2 / (4 pi^2). Substituting into x = (m/k) g gives **x = g T^2 / (4 pi^2)**. Notice the mass cancels out entirely.


> **NOTE: PYQ worked out**
>
> "A body of mass 4.9 kg hangs from a spring and oscillates with a period of 0.6 sec. How much will the spring shorten when the body is removed?"
>
> Answer: **0.089 metre**
>
> Use the derived formula (the mass is not even needed):
> x = g T^2 / (4 pi^2)
>
> Substitute g = 9.8 m/s^2, T = 0.6 s:
> x = (9.8 x 0.6 x 0.6) / (4 x 3.1416 x 3.1416)
> = (9.8 x 0.36) / (39.478)
> = 3.528 / 39.478
> = **0.0894 m**, which is approximately **0.089 metre**
>
> Note the distractors 0.809, 1.089 and 1.009 - all are digit rearrangements of the correct 0.089, a classic trap. Also note that the given mass 4.9 kg is a **red herring**: it cancels out, because a heavier mass stretches the spring more but also oscillates more slowly, and the two effects exactly compensate.



### J5.5 Cells in series and terminal voltage


- **EMF** - The electromotive force, the voltage a cell produces on open circuit.
- **Internal resistance (r)** - The resistance inside the cell itself.
- **Terminal potential difference** - V = EMF - I r. It is always less than the EMF when current flows.
- **Cells in SERIES** - Total EMF = sum of individual EMFs. Total internal resistance = sum of internal resistances.
- **Cells in PARALLEL (identical)** - Total EMF = EMF of one cell. Total internal resistance = r / n.


> **NOTE: PYQ worked out (this question appeared in Hindi)**
>
> "Two identical cells of emf 1.5 V and internal resistance 0.5 ohm are connected in series. If the current allowed from the cell is 1 A, then the effective terminal potential difference of the cell will be ______."
>
> Answer: **2 V**
>
> Step 1 - combine the cells in series.
> Total EMF = 1.5 + 1.5 = **3 V**
> Total internal resistance = 0.5 + 0.5 = **1 ohm**
>
> Step 2 - apply V = EMF - I r.
> V = 3 - (1 A x 1 ohm) = 3 - 1 = **2 V**
>
> The distractors check specific errors: **1 V** would come from using only one cell (1.5 - 0.5); **0.75 V** from a parallel-connection mistake; **0.5 V** from confusing the internal resistance with the answer.



### J5.6 Magnetism - bar magnet and solenoid


- **Magnetic moment of a bar magnet** - M = m x 2l (pole strength times length).
- **Magnetic moment of a solenoid** - M = N I A (number of turns x current x area).
- **The equivalence principle** - A current-carrying solenoid behaves exactly like a bar magnet. If the two produce the **same magnetic field**, then they must have the **same magnetic moment** - that is precisely what "equivalent" means.


> **NOTE: PYQ worked out**
>
> "The magnetic moment of a bar magnet is _____ the magnetic moment of an equivalent solenoid if the solenoid's magnetic field is _______ that of the bar magnet."
>
> Answer: **equal to ; same as**
>
> The logic is definitional. An "**equivalent** solenoid" means one that reproduces the bar magnet's magnetic behaviour. If the fields are the **same**, the sources must have the **same magnetic moment** - because the external field of a magnetic dipole is determined entirely by its magnetic moment.
>
> So: same field implies equal magnetic moment. The other options ("more than", "less than", "different from") break the equivalence.



## J6 Accountancy and Business Economics Essentials



### J6.1 Basic accounting concepts


- **Double entry system** - Every transaction affects **two** accounts and is recorded with a **DEBIT and a CREDIT** of equal amount. Total debits always equal total credits.
- **Golden rules** - Personal accounts: debit the receiver, credit the giver. Real accounts: debit what comes in, credit what goes out. Nominal accounts: debit expenses and losses, credit incomes and gains.
- **Journal** - The book of original entry, recording transactions chronologically.
- **Ledger** - Accounts classified by head.
- **Trial balance** - A list of all ledger balances, used to check that debits equal credits.


> **NOTE: Direct PYQ**
>
> "According to the double entry system, every transaction will have ______ entries." Options: Right and Left, Up and Down, **Debt and Credit**, Up and Left. Answer: **Debt and Credit** (the paper's spelling of **Debit and Credit**).
>
> Every transaction has a debit side and a credit side of equal value. This is the foundation of all accounting.



### J6.2 Final accounts



| Statement | What it shows | Key output |
|---|---|---|
| Trading account | Buying and selling of goods only | GROSS PROFIT (or gross loss) |
| PROFIT AND LOSS ACCOUNT | All other incomes and expenses | **NET PROFIT** (or net loss) |
| Balance sheet | Assets, liabilities and capital on a particular DATE | The financial POSITION. It is a statement, not an account |



*The two profit formulas*
```
Gross Profit = Net Sales - Cost of Goods Sold (COGS)

  where COGS = Opening Stock + Purchases + Direct Expenses (e.g. Wages)
               - Closing Stock

Net Profit   = Gross Profit + Other Incomes - Indirect Expenses
```



> **NOTE: Direct PYQ**
>
> "Which of the following accounts is/are prepared for net profit?" Answer: **Profit and loss account**.
>
> The trading account gives **gross** profit; the profit and loss account gives **net** profit; the balance sheet shows position rather than profit. Keep the pair straight: **Trading = Gross, P&L = Net.**



### J6.3 Assets, liabilities and capital



| Term | Meaning | Examples |
|---|---|---|
| FIXED ASSETS | LONG-TERM assets held for use in the business for more than one year, not for resale | Land, building, plant and machinery, furniture, vehicles |
| Current assets | Convertible into cash within one year | Cash, bank, debtors, stock, prepaid expenses |
| Tangible assets | Have a physical existence | Building, machinery |
| Intangible assets | No physical existence but have value | Goodwill, patents, trademarks, copyrights |
| Fixed liabilities / Long-term liabilities | Payable after more than one year | Debentures, long-term loans |
| Current liabilities | Payable within one year | Creditors, bills payable, outstanding expenses, income received in advance |
| Capital | The owner's investment in the business | - |
| DRAWINGS | **Any account or goods used by the OWNER of the business for his PERSONAL use.** It reduces capital | Owner takes cash or stock home |


- **Accounting equation** - **Assets = Liabilities + Capital.**
- **WORKING CAPITAL** - **The part of the firm's capital required for conducting DAY-TO-DAY expenses** and short-term operations. Working Capital = Current Assets - Current Liabilities.
- **Fixed capital** - The capital invested in fixed assets.


> **NOTE: Three direct PYQs**
>
> "What is a long-term asset in accounting?" Options: Intangible assets, Current liabilities, Fixed liabilities, **Fixed assets**. Answer: **Fixed assets**. (Note: intangible assets *can* be long-term, but "fixed assets" is the standard term for long-term assets held for use.)
>
> "Any account or goods used by the owner of the business for his personal use is called as:" Options: sales, **drawings**, general expenses, expenses. Answer: **drawings**.
>
> "The part of the firm's capital that is required for conducting day to day expenses is called:" Answer: **working capital**. The phrase "day to day" is the trigger - long-term needs are met by *fixed* capital.



### J6.4 Solved accounting numericals



> **NOTE: PYQ worked out - gross profit on sales**
>
> "During the financial year 2024-25 the total purchases of ABC Limited were Rs. 1,90,000. If ABC Limited's gross profit was 20% on sales and the closing stock was Rs. 30,000 more than the opening stock, what was the gross profit earned during 2024-25?"
>
> Answer: **Rs. 40,000**
>
> Step 1 - work out the cost of goods sold.
> COGS = Opening Stock + Purchases - Closing Stock
>
> We are told Closing Stock = Opening Stock + 30,000. Substituting:
> COGS = Opening + 1,90,000 - (Opening + 30,000)
> = 1,90,000 - 30,000
> = **Rs. 1,60,000**
>
> Notice the opening stock cancels out - we never needed its value.
>
> Step 2 - use the gross profit percentage.
> Gross profit is **20% ON SALES**, so:
> Gross Profit = 0.20 x Sales
> COGS = Sales - Gross Profit = Sales - 0.20 Sales = **0.80 x Sales**
>
> Therefore Sales = COGS / 0.80 = 1,60,000 / 0.80 = **Rs. 2,00,000**
>
> Step 3 - compute the gross profit.
> Gross Profit = 20% of 2,00,000 = **Rs. 40,000**
>
> **The trap in this question:** "20% on sales" is NOT the same as "20% on cost". If it were 20% on cost, the gross profit would be 20% of 1,60,000 = Rs. 32,000. Always check which base the percentage refers to.



> **NOTE: PYQ worked out - loss of stock by fire**
>
> "On 15 December 2024, a fire occurred in the godown of M Ltd., and the entire stock was destroyed. The value of the stock salvaged was Rs. 3,00,000... The value of stock lost by fire was ____."
>
> Answer: **Rs. 6,30,000**
>
> The method for every "stock destroyed by fire" question:
>
> **Step 1** - find the closing stock on the date of the fire, using the trading-account logic:
> Stock on date of fire = Opening Stock + Purchases + Direct Expenses (Wages)
> - Cost of Goods Sold
>
> **Step 2** - find COGS from the sales and the gross profit rate:
> COGS = Sales - Gross Profit = Sales x (1 - gross profit rate)
>
> **Step 3** - subtract what was saved:
> **Stock lost by fire = Stock on date of fire - Stock salvaged**
>
> Here the salvaged stock was Rs. 3,00,000, and applying the above with the figures in the question's table gives a stock-on-hand of Rs. 9,30,000, so the loss is
> 9,30,000 - 3,00,000 = **Rs. 6,30,000**
>
> **Remember the three steps.** Even if the table figures differ in your exam, the structure is always: build up the stock, subtract COGS, then subtract salvage.



> **NOTE: PYQ worked out - income received in advance**
>
> "MC Publications has received rent amounting to Rs. 2,50,000 during the financial year ending 31 March 2024. Out of this Rs. 50,000 represents rent relating to next financial year. The rent account to be credited to the profit and loss account for the year ended 31 March 2024 is ________ and the rent received in advance will be shown as a/an ________."
>
> Answer: **Rs. 2,00,000 ; Liability**
>
> Two accounting principles are being tested.
>
> **First, the accrual (matching) concept.** Only income *earned during this year* may be credited to this year's profit and loss account.
> Rent for this year = 2,50,000 - 50,000 = **Rs. 2,00,000**
>
> **Second, the treatment of income received in advance.** The Rs. 50,000 has been received but not yet earned - the business still *owes* the service (accommodation) for next year. An obligation to provide something is a **LIABILITY**, shown on the liabilities side of the balance sheet as "Rent received in advance" (also called unearned income).
>
> The trap: many candidates mark it as an **asset** because cash came in. Remember that the *cash* is an asset, but the *unearned portion* creates a matching **liability**.



### J6.5 Forms of business organisation



| Form | Ownership | Liability | Members |
|---|---|---|---|
| SOLE PROPRIETORSHIP | ONE person who carries on business BY HIMSELF/HERSELF | UNLIMITED | 1. THE MOST COMMON form of business organisation |
| Partnership | Two or more persons | Unlimited (except LLP) | Minimum 2; maximum 50 under the Companies Act rules |
| Hindu Undivided Family (HUF) | Family members by birth | Karta unlimited, others limited | - |
| Cooperative society | Members, democratic, one member one vote | Limited | Minimum 10 |
| COMPANY (private) | Shareholders; separate legal entity | **LIMITED liability** | Minimum 2, maximum 200 |
| COMPANY (public) | Shareholders; shares freely transferable | LIMITED liability | MINIMUM 7, no maximum |



> **NOTE: Three direct PYQs on business forms**
>
> "The most common type of business organisation is:" Answer: **sole proprietorship** - because it is the easiest and cheapest to start, needs no registration formalities, and covers the vast majority of small shops and traders.
>
> "______ is a person who carries on business by himself/herself." Answer: **Sole proprietorship**.
>
> "Which of the following business structures has limited liability to its members?" Options: Partnership, Cooperative society, **Company**, Sole proprietorship. Answer: **Company**. In a company the members' liability is limited to the unpaid amount on their shares, because the company is a **separate legal person** from its owners. A partnership and a sole proprietorship both carry unlimited liability. (A cooperative society also has limited liability, but "Company" is the standard textbook answer for limited liability.)
>
> "A public company must have at least ______ members." Answer: **7**. Learn the pair: **private company minimum 2, public company minimum 7.**



### J6.6 Business activities and organisation structure



| Sector | Activities |
|---|---|
| Primary | Extraction from nature: agriculture, mining, fishing, forestry |
| Secondary | **MANUFACTURING** and construction - converting raw materials into finished goods |
| Tertiary (services) | Trade, TRANSPORTATION, WAREHOUSING, INSURANCE, banking, advertising, communication - services that AID trade |



> **NOTE: Direct PYQ**
>
> "Which of the following is NOT a tertiary business activity?" Options: Transportation, Warehousing, Insurance, **Manufacturing**. Answer: **Manufacturing**.
>
> Manufacturing is a **secondary** (industrial) activity - it physically makes goods. Transportation, warehousing and insurance are all **auxiliaries to trade**, which is the definition of tertiary/service activity.


- **Organisation structure** - Establishes relationships between **people, work and resources** - who does what work, with what resources, and who reports to whom.
- **Delegation** - Passing authority and responsibility down to a subordinate. **Delegation on a wide scale across the organisation leads to DECENTRALISATION.**
- **Centralisation** - Decision-making authority concentrated at the top.
- **Decentralisation** - Systematic dispersal of decision-making authority to lower levels. It is the *result* of extensive delegation.
- **Authority** - The right to command.
- **Responsibility** - The obligation to perform.
- **Accountability** - Answerability for the outcome. Authority can be delegated; **accountability cannot**.


> **NOTE: Two direct PYQs**
>
> "An organisation structure establishes relationships between:" Answer: **people, work and resources**.
>
> "Which of the following statement is correct for a business organisation?" Options: Responsibility leads to decentralisation / Authority leads to decentralisation / **Delegation leads to decentralisation** / Centralisation leads to autonomy. Answer: **Delegation leads to decentralisation**.
>
> The causal chain: a manager **delegates** authority to a subordinate; when this happens systematically throughout the organisation, decision-making becomes dispersed, which **is** decentralisation. Note that "centralisation leads to autonomy" is the exact opposite of the truth - decentralisation gives autonomy.



### J6.7 Business economics - demand and forecasting


- **Demand** - The quantity of a good consumers are willing AND able to buy at a given price. It is often defined as **effective desire** - desire backed by purchasing power and willingness to spend.
- **Utility** - The satisfaction derived from consuming a good.
- **Law of demand** - Other things being equal, as price rises quantity demanded falls (an inverse relationship).
- **ELASTICITY OF DEMAND** - Measures the **DEGREE** of responsiveness of quantity demanded to a change in price. It explains the **degree** of the correlation between price and quantity. Ed = (percentage change in quantity) / (percentage change in price).
- **Marginal revenue** - The addition to total revenue from selling one more unit. **MR = change in Total Revenue / change in Total Output Quantity.**
- **Marginal cost** - The addition to total cost from producing one more unit. MC = change in Total Cost / change in Output.


> **NOTE: Three direct PYQs**
>
> "Elasticity of demand explains the ______ of the correlation between price and quantity." Options: level, degree and angle / angle / level / **degree**. Answer: **degree**. Elasticity is a *measure of magnitude* - how strongly quantity responds - so "degree" is the right word.
>
> "Marginal revenue is calculated by ______." Answer: **dividing the change in total revenue by the change in total output quantity**. Note the order carefully: revenue change on top, quantity change at the bottom. The distractor that inverts them (quantity divided by revenue) is wrong, and the one using total *cost* defines marginal cost instead.
>
> "What is effective desire?" The paper's key gave **Consumption**. Note that in standard economics, **effective desire is the definition of DEMAND** - desire plus ability plus willingness to pay. If both "Demand" and "Consumption" appear, the theoretically correct answer is **Demand**; this particular key chose Consumption. Be aware of the discrepancy.



#### Methods of demand forecasting


| Method | Description |
|---|---|
| Survey methods | Asking people directly |
| -- Consumer interview / Complete enumeration | Ask all or a sample of consumers about their buying intentions |
| -- OPINION SURVEY (Sales-Force-Composite method / COLLECTIVE OPINION method) | Ask the firm's own SALES STAFF and experts to estimate demand in their territories, then combine those estimates |
| -- Delphi method | Repeated rounds of anonymous expert opinion until consensus |
| Statistical methods | Using past data |
| -- Trend projection | Extend the past trend into the future |
| -- Regression analysis | Model demand as a function of its determinants |
| -- Barometric technique | Use leading indicators |
| Methods for NEW products | Where no past data exists |
| -- EVOLUTIONARY approach | Treat the new product as an EVOLUTION of an existing product and project from the existing product's demand |
| -- SUBSTITUTE approach | Treat the new product as a SUBSTITUTE; the GROWTH OF AN EXISTING PRODUCT is used to estimate demand for the new one |
| -- VICARIOUS approach | Survey consumers indirectly through dealers and retailers |
| -- Growth curve approach | Base the forecast on the growth curve of a similar established product |
| -- Sales experience / test marketing | Launch in a small area first |



> **NOTE: Three direct PYQs on forecasting**
>
> "______ is also referred to as the Sales-Force-Composite method or the Collective Opinion Method." Answer: **Opinion survey**. Both alternative names refer to collecting and combining the *opinions* of the sales force.
>
> "According to business economics, the growth of an existing product is used to estimate the demand for a new product using:" Answer: **substitute approach**. The new product is assumed to substitute for the existing one, so the existing product's growth indicates the new one's potential.
>
> "Which method is used for demand forecasting of new products?" Answer: **Evolutionary approach, opinion polling approach and vicarious approach** (all three). For a brand-new product there is no sales history, so firms use several of these indirect techniques together. When an option lists all the valid methods and the others list only one each, the "all of these" style option is usually correct - provided every item in it is genuinely valid.



### J6.8 Inflation and business types



| Type of inflation | Cause |
|---|---|
| DEMAND-PULL inflation | **DEMAND for goods and services exceeds supply, so demand DRIVES UP PRICES.** "Too much money chasing too few goods" |
| Cost-push inflation | Rising costs of production (wages, raw materials, oil) push prices up, even without extra demand |
| Built-in inflation | Workers demand higher wages to match past inflation, which raises costs, which raises prices - a wage-price spiral |
| Stagflation | High inflation together with high unemployment and stagnant growth |
| Deflation | A general fall in the price level |



> **NOTE: Direct PYQ**
>
> "Which of the following inflations describes how demand for goods and services can drive up their prices?" Options: Cost-push inflation, Built-in Inflation, **Demand-pull inflation**, Demand-push inflation. Answer: **Demand-pull inflation**.
>
> Watch the distractor "**Demand-push** inflation" - it does not exist. The correct pair of terms is **demand-PULL** (demand pulls prices up) and **cost-PUSH** (costs push prices up). Mixing the two words is the most common error.



#### Types of business by driver


> **NOTE: Direct PYQ**
>
> "Which of the following is NOT a type of business?" Options: Experience driven, **Expense driven**, Efficiency driven, Expert driven. Answer: **Expense driven**.
>
> In the knowledge-management and business-strategy literature, businesses are classified as **experience-driven**, **efficiency-driven** and **expert-driven** (based on whether they compete through accumulated experience, operational efficiency, or specialist expertise). "Expense-driven" is not one of these categories - no business is defined by its expenses.



### J6.9 Entrepreneurship and applied mathematics


- **Bootstrapping** - **Self-funding a business using personal resources** - own savings, revenue from early customers, personal credit - rather than raising outside money. The opposite of raising venture capital, bank loans or crowdfunding.
- **Venture capital** - Professional investors funding high-growth start-ups in exchange for equity.
- **Angel investor** - A wealthy individual investing early-stage money.
- **Crowdfunding** - Raising small amounts from many people online.


> **NOTE: Direct PYQ**
>
> "What does the term 'bootstrapping' refer to in the context of starting a business?" Answer: **Self-funding the business using personal resources.** The image behind the word is "pulling yourself up by your own bootstraps" - progressing without outside help. All three distractors involve **external** money (venture capital, bank loans, crowdfunding), which is exactly what bootstrapping avoids.


- **Operations Research (OR)** - The application of **advanced analytical and mathematical methods** - linear programming, queuing theory, simulation, game theory, network analysis - to improve decision-making. It is a branch of **APPLIED MATHEMATICS**.


> **NOTE: Direct PYQ**
>
> "Which of the following comes under applied mathematics?" Options: Information processing, **Operations research**, Management accounting, Organisation. Answer: **Operations research**.
>
> Operations Research is universally classified as applied mathematics - it uses mathematical optimisation and probability models to solve real decision problems. Information processing is computing, management accounting is commerce, and organisation is management theory.

