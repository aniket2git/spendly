
---

# PART 10 - Mathematics, Statistics and the DSSSB-Specific Topics

> *Weightage: 4 to 8 marks (Maths/Stats) plus 6 to 10 marks (Physics / Accounting / Economics) in DSSSB. Largely absent from KVS and NVS Computer Science papers.*



> **NOTE: Read this before you study this Part**
>
> This Part exists because **DSSSB draws its Discipline sections from the wider graduate stream**, so Physics, Accountancy and Business Economics questions appear alongside the computing ones. In the three papers you shared these were worth **6 to 10 marks per paper**.
>
> **If you are sitting only KVS or NVS Computer Science, you may safely de-prioritise Chapter 10.3 onwards.** If you are sitting DSSSB, you cannot - it is too many marks to abandon.
>
> The strategy is narrow and deliberate: learn the **specific formulas** below, not the subjects. Almost every question in those papers was a one-step formula application. If a question needs more than one unfamiliar step, skip it.



## 10.1 Numerical Methods



> **WEIGHTAGE: 1-3 marks in DSSSB | Interpolation and difference operators recur | Priority MEDIUM**



### 10.1.1 Questions



**Q. [PYQ] Interpolation is carried out using data from:**

- (a) regression analysis
- (b) curve fitting and regression analysis
- (c) linear interpolation
- (d) **curve fitting and linear analysis  <-- CORRECT**

> **Why:** The distinguishing fact: **interpolation passes exactly through every known data point**, whereas **regression** finds a best-fit line that need not pass through any of them. So any option mentioning regression is wrong.



**Q. [PYQ] Which method creates interpolants that are softer?**

- (a) Polynomial and spline interpolation
- (b) **Piecewise constant interpolation  <-- CORRECT**
- (c) Polynomial interpolation
- (d) Linear interpolation and spline interpolation

> **Why:** Piecewise constant (nearest-neighbour) interpolation produces a plain **step function** with no curvature at all - the crudest and "softest" interpolant. **Spline** interpolation is the smoothest practical choice; high-degree **polynomial** interpolation oscillates badly near the edges (Runge's phenomenon).



**Q. [PYQ] The ______ interpolation method is used in probability theory and statistics, and the Gaussian process is one example.**

- (a) linear
- (b) polynomial
- (c) spline
- (d) **nonlinear  <-- CORRECT**

> **Why:** The **Gaussian process** (also called kriging) is a nonlinear, probabilistic interpolation technique used heavily in statistics and machine learning. Linear, polynomial and spline interpolation are deterministic curve fits.



**Q. [PYQ] [NUMERICAL] The values of x are 1, 3, 4 and those of f(x) are 1, 27, 64. What is the polynomial using the Lagrange interpolation formula?**

- (a) **8x^2 - 19x + 12  <-- CORRECT**
- (b) 8x^2 + 9x + 12
- (c) 8x^2 - 9x + 12
- (d) 8x^2 + 9x + 12

> **Why:** **Do not expand the Lagrange formula under exam pressure - verify the options instead.** The correct polynomial must reproduce every data point. Test 8x^2 - 19x + 12: at x=1, 8-19+12 = **1**; at x=3, 72-57+12 = **27**; at x=4, 128-76+12 = **64**. All match. Test a distractor 8x^2+9x+12 at x=1: 8+9+12 = 29, not 1 - fails immediately. **Substitute the smallest x into each option; usually three fail at once.**



**Q. [PYQ] [NUMERICAL] What is the value of Delta^n of e^(ax+b)?**

- (a) (e^(ah) - 1)^n e^(ax-b)
- (b) **(e^(ah) - 1)^n e^(ax+b)  <-- CORRECT**
- (c) (e^(ah) + 1)^n e^(ax-b)
- (d) (e^(ah) + 1)^n e^(ax+b)

> **Why:** Compute one difference and spot the pattern: Delta e^(ax+b) = e^(a(x+h)+b) - e^(ax+b) = e^(ax+b)(e^(ah) - 1). So each application multiplies by the factor **(e^(ah) - 1)**, and n applications give **(e^(ah) - 1)^n e^(ax+b)**. Check two things in the options: the sign inside the bracket must be **minus**, and the exponent must remain **ax + b** (differencing never alters b).



**Q. [PYQ] [NUMERICAL] If mu is an averaging operator and delta is the central difference operator, what is mu^2?**

- (a) **mu^2 = (1/4)(delta^2 + 4)  <-- CORRECT**
- (b) mu^2 = (1/2)(delta^2 + 4)
- (c) mu^2 = (1/4)(delta^2 + 6)
- (d) mu^2 = (1/4)(delta^2 + 8)

> **Why:** From mu = (E^(1/2) + E^(-1/2))/2, squaring gives mu^2 = (E + 2 + E^(-1))/4. Since delta = E^(1/2) - E^(-1/2), delta^2 = E - 2 + E^(-1), so **E + E^(-1) = delta^2 + 2**. Substituting: mu^2 = (delta^2 + 2 + 2)/4 = **(delta^2 + 4)/4**. Remember the pair of numbers: **one quarter, plus four.**



**Q. [EXPECTED] The relation between the forward difference operator and the shift operator is:**

- (a) Delta = E + 1
- (b) **Delta = E - 1  <-- CORRECT**
- (c) Delta = 1 - E
- (d) Delta = E

> **Why:** Since Delta f(x) = f(x+h) - f(x) and E f(x) = f(x+h), we get **Delta = E - 1**, equivalently **E = 1 + Delta**. Also: nabla = 1 - E^(-1), and delta = E^(1/2) - E^(-1/2).



## 10.2 Probability and Statistics



> **WEIGHTAGE: 2-4 marks in DSSSB | Priority MEDIUM**



### 10.2.1 Questions



**Q. [PYQ] Who invented the probability definition?**

- (a) **Simon Laplace  <-- CORRECT**
- (b) Euclid
- (c) None of the given answer
- (d) Einstein

> **Why:** **Pierre-Simon Laplace** gave the classical definition (favourable outcomes over total equally likely outcomes) in 1812. Euclid is geometry.



**Q. [PYQ] Which probability calculus of views obeys particular rules?**

- (a) Standard deviation
- (b) Variance
- (c) **Bayesian probability  <-- CORRECT**
- (d) Frequency probability

> **Why:** The phrase "calculus of **views**" is the clue: **Bayesian** probability treats probability as a **degree of belief** that is updated as evidence arrives, according to fixed rules. Standard deviation and variance are measures of *spread*, not interpretations of probability.



**Q. [PYQ] [NUMERICAL] If two dice are thrown, find the probability that the sum is neither 5 nor 9.**

- (a) 3/9
- (b) 5/9
- (c) 1/9
- (d) **7/9  <-- CORRECT**

> **Why:** Total outcomes = 36. Sum 5 occurs 4 ways (1+4, 2+3, 3+2, 4+1); sum 9 occurs 4 ways (3+6, 4+5, 5+4, 6+3). So P(5 or 9) = 8/36 = 2/9, and P(neither) = 1 - 2/9 = **7/9**. **Whenever a question says "neither/nor" or "not", count the unwanted cases and subtract from 1.**



**Q. [PYQ] [NUMERICAL] A six-faced die is thrown. The probability that the number on top is even is:**

- (a) 1/4
- (b) 1/6
- (c) **1/2  <-- CORRECT**
- (d) 1/9

> **Why:** Even outcomes {2, 4, 6} out of 6 gives 3/6 = **1/2**. The distractor 1/6 is the probability of one *specific* number.



**Q. [PYQ] [NUMERICAL] Eighty-eight residents are classified as male/female and as tea drinkers/non-drinkers. For testing association between sex and tea drinking, the test statistic follows:**

- (a) t distribution with 1 degree of freedom
- (b) Chi Square distribution with 2 degrees of freedom
- (c) Normal distribution
- (d) **Chi square distribution with 1 degree of freedom  <-- CORRECT**

> **Why:** Testing **association between two categorical variables** means a **chi-square test of independence**, which eliminates the t and normal options. Degrees of freedom = **(r-1)(c-1)** = (2-1)(2-1) = **1**. Note the sample size 88 is a red herring - it never enters the df calculation.



**Q. [PYQ] [TRAP] The algebraic sum of deviations is zero when measured from the ______.**

- (a) second quartile
- (b) geometric mean
- (c) **arithmetic mean  <-- CORRECT**
- (d) harmonic mean

> **Why:** Proof in one line: SUM(x - mean) = SUM x - n(mean), and since mean = (SUM x)/n we have n(mean) = SUM x, so the difference is **0**. Verify with 2, 4, 6: mean is 4 and deviations -2, 0, +2 sum to zero. Related property: the sum of *squared* deviations is **minimum** about the arithmetic mean.



**Q. [PYQ] Identify the generic probability density function that corresponds with discrete random variables.**

- (a) Cumulative distribution
- (b) Gaussian distribution
- (c) **Poisson distribution  <-- CORRECT**
- (d) Rayleigh distribution

> **Why:** **Poisson** is the discrete one - it counts whole numbers of rare events (0, 1, 2, ...) and has the special property **mean = variance = lambda**. Gaussian and Rayleigh are **continuous**; "cumulative distribution" is a general concept applying to both.



**Q. [EXPECTED] For a binomial distribution, the mean is:**

- (a) np(1-p)
- (b) **np  <-- CORRECT**
- (c) p/n
- (d) n/p

> **Why:** Mean = **np**, variance = **npq** where q = 1-p. Binomial counts successes in n independent trials.



**Q. [EXPECTED] [TRAP] In a perfectly symmetric normal distribution:**

- (a) mean > median > mode
- (b) mean < median < mode
- (c) **mean = median = mode  <-- CORRECT**
- (d) mode is undefined

> **Why:** This equality is the signature of the normal (Gaussian) bell curve. In a **positively skewed** distribution mean > median > mode; in a **negatively skewed** one the order reverses.



**Q. [EXPECTED] Which measure of central tendency is least affected by extreme values?**

- (a) Arithmetic mean
- (b) **Median  <-- CORRECT**
- (c) Geometric mean
- (d) Range

> **Why:** The **median** depends only on position, not magnitude, so a single outlier cannot drag it. The mean is highly sensitive. Also remember **AM >= GM >= HM** always.



## 10.3 Calculus, Matrices and Differential Equations



> **WEIGHTAGE: 2-4 marks in DSSSB | Priority MEDIUM (skip for KVS/NVS)**



### 10.3.1 Questions



**Q. [PYQ] [NUMERICAL] The series SUM 1/(n^2) raised to the power 1/5 is:**

- (a) None of the given options
- (b) divergent
- (c) oscillatory convergent
- (d) **convergent  <-- CORRECT**

> **Why:** **KEY NOTE.** Simplify first: 1/(n^2)^(1/5) = 1/n^(2/5), a **p-series with p = 0.4**. The standard rule is that SUM 1/n^p **converges if p > 1 and diverges if p <= 1**, which makes this **divergent** - yet the official key marked it convergent. Learn the rule properly: SUM 1/n diverges (harmonic), SUM 1/n^2 converges, SUM 1/sqrt(n) diverges.



**Q. [PYQ] [NUMERICAL] If u = tan inverse (y/x), then x du/dx + y du/dy = ?**

- (a) Sin 2u
- (b) **0  <-- CORRECT**
- (c) None of the given options
- (d) Cos 2u

> **Why:** Use **Euler's theorem**: if f is homogeneous of degree n then x fx + y fy = n f. Here u(tx, ty) = arctan(ty/tx) = arctan(y/x) = t^0 u, so u is homogeneous of **degree 0** and the answer is 0 x u = **0**. Key insight: **any function of the pure ratio y/x is homogeneous of degree zero**, so this expression is always 0.



**Q. [PYQ] [NUMERICAL] Find a unit vector normal to the surface x^3 + y^3 + 3xyz = 3 at the point (1, 2, -1).**

- (a) (1/sqrt2)(i - 3j - 2k)
- (b) (1/sqrt14)(i - 3j + 2k)
- (c) **(1/sqrt14)(-i + 3j + 2k)  <-- CORRECT**
- (d) (i + 3j + 2k)

> **Why:** The **gradient is normal to the surface**. Partials: dF/dx = 3x^2+3yz = 3-6 = **-3**; dF/dy = 3y^2+3xz = 12-3 = **9**; dF/dz = 3xy = **6**. So grad F = -3i+9j+6k = 3(-i+3j+2k). Magnitude of the bracket = sqrt(1+9+4) = **sqrt14**. Unit normal = **(-i+3j+2k)/sqrt14**. Always factor out the common term *before* computing the magnitude.



**Q. [PYQ] [NUMERICAL] The volume of the tetrahedron bounded by x = 0, y = 0, z = 0 and x/a + y/b + z/c = 1 is:**

- (a) abc/4
- (b) abc/2
- (c) abc/10
- (d) **abc/6  <-- CORRECT**

> **Why:** A standard result worth memorising. The plane cuts the axes at (a,0,0), (0,b,0), (0,0,c), forming a tetrahedron with three mutually perpendicular edges. Volume = (1/3)(base area)(height) = (1/3)(ab/2)(c) = **abc/6**. Hook: the corner tetrahedron is exactly **one sixth** of the cuboid with sides a, b, c.



**Q. [PYQ] [NUMERICAL] The characteristic equation of A = [[1,4],[3,5]] is:**

- (a) lambda^2 + 6lambda - 7 = 0
- (b) lambda^2 - 6lambda + 7 = 0
- (c) **lambda^2 - 6lambda - 7 = 0  <-- CORRECT**
- (d) lambda^2 + 6lambda + 7 = 0

> **Why:** For any 2x2 matrix use **lambda^2 - (trace)lambda + (determinant) = 0**. Trace = 1+5 = **6**; determinant = (1)(5)-(4)(3) = **-7**. So lambda^2 - 6lambda - 7 = 0. Watch both signs: the trace term is always *minus* trace, and here the determinant is itself negative.



**Q. [PYQ] [NUMERICAL] If A = [[1,0,0],[0,-1,0],[1,0,1]] then A^6 is:**

- (a) [[6,0,0],[0,6,0],[6,0,6]]
- (b) [[1,0,0],[0,-1,0],[6,0,1]]
- (c) [[1,0,0],[0,-1,0],[1,0,1]]
- (d) **[[1,0,0],[0,1,0],[6,0,1]]  <-- CORRECT**

> **Why:** **Compute A^2, spot the pattern, then jump.** A^2 gives [[1,0,0],[0,1,0],[2,0,1]] - the (2,2) entry becomes (-1)^n and the (3,1) entry becomes n. For n = 6 (even), (-1)^6 = **+1** and the (3,1) entry = **6**. Use **parity**: an even power always turns a -1 diagonal entry into +1.



**Q. [PYQ] [NUMERICAL] Which differential equation corresponds to y = a e^(2x) + b e^(-x)?**

- (a) y'' - 2y' + y = 0
- (b) y'' + 2y' + y = 0
- (c) y'' + y' - 2y = 0
- (d) **y'' - y' - 2y = 0  <-- CORRECT**

> **Why:** **Read the exponents off the solution** - they are the roots of the auxiliary equation. Roots 2 and -1 give (m-2)(m+1) = m^2 - m - 2 = 0, and replacing m^2 with y'', m with y' and the constant with y gives **y'' - y' - 2y = 0**. Verify with y = e^(2x): 4e - 2e - 2e = 0. Correct.



**Q. [PYQ] [NUMERICAL] The general solution of dy/dx = e^(x+y) is:**

- (a) e^(-x) - e^(-y) = c
- (b) e^(-x) + e^y = c
- (c) **e^x + e^(-y) = c  <-- CORRECT**
- (d) e^(-x) + e^y = c

> **Why:** Separate: e^(x+y) = e^x . e^y, so e^(-y) dy = e^x dx. Integrating gives -e^(-y) = e^x + k, and rearranging gives **e^x + e^(-y) = c**. The sign flip comes from integrating e^(-y), which yields *minus* e^(-y).



**Q. [PYQ] [NUMERICAL] [TRAP] The particular solution of y'' - 6y' + 9y = 2e^(3t) is:**

- (a) e^(3t)/2
- (b) **t^2 e^(3t)  <-- CORRECT**
- (c) e^(3t)
- (d) e^(3t)/9

> **Why:** The auxiliary equation m^2-6m+9 = (m-3)^2 = 0 has **m = 3 as a DOUBLE root**, and the forcing term is e^(3t) - the resonance case. **Rule: if r is not a root, PI is proportional to e^(rt); if r is a simple root, multiply by t; if r is a double root, multiply by t^2.** Hence **t^2 e^(3t)**. The same idea appeared again as (D^4 - 18D^2 + 81)y, which factors to (D-3)^2(D+3)^2 and gives x^2 e^(3x).



## 10.4 Physics Topics That Appeared



> **WEIGHTAGE: 3-5 marks in DSSSB only | Priority LOW for KVS/NVS**



### 10.4.1 Questions



**Q. [PYQ] [NUMERICAL] An LED emits green light of wavelength 5511.11 Angstrom. Find Eg.**

- (a) 1.25 eV
- (b) **2.25 eV  <-- CORRECT**
- (c) 3.606 eV
- (d) 36.06 eV

> **Why:** Memorise the shortcut: **E (in eV) = 12400 / lambda (in Angstrom)** = 12400/5511.11 = **2.25 eV**. The distractor 3.606 is the answer in units of 10^-19 **joules** mistaken for eV - always finish the conversion.



**Q. [PYQ] What is the lifetime of an atom's ground state in stimulated absorption?**

- (a) 2 minutes
- (b) 11 hours
- (c) 5 seconds
- (d) **Infinity  <-- CORRECT**

> **Why:** The **ground state is the lowest energy level** - there is nowhere lower for the atom to fall to, so without external excitation it remains there indefinitely. Contrast an ordinary excited state (about 10^-8 s) and a **metastable** state (about 10^-3 s), whose long life is what makes population inversion possible.



**Q. [PYQ] Which transition generates laser output in the CO2 molecule?**

- (a) **Vibrational states  <-- CORRECT**
- (b) Pulsed output
- (c) Molecular states
- (d) Energy states

> **Why:** CO2 is a **molecule**, so it has vibrational and rotational levels in addition to electronic ones; lasing occurs between **vibrational** states, emitting at 10.6 micrometres. "Pulsed output" describes a mode of operation, not a transition.



**Q. [PYQ] Which phenomenon causes a phase shift in the retardation plates?**

- (a) Phasor plates
- (b) Retardation plates
- (c) Polaroid filters
- (d) **Double refraction  <-- CORRECT**

> **Why:** The causal chain: the plate is made of a **birefringent (doubly refracting)** crystal, so the two polarisation components see different refractive indices, travel at different speeds and emerge with a **phase difference**. Note "retardation plates" is offered as an option - but that is the *device*, not the *phenomenon*.



**Q. [PYQ] Does polarisation vary with direction?**

- (a) Polarising axis
- (b) **Transverse wave  <-- CORRECT**
- (c) Propagating axis
- (d) Pass axis

> **Why:** Polarisation exists **only because light is a transverse wave** - the oscillation is perpendicular to the direction of travel, so there is a choice of direction. **Longitudinal waves such as sound cannot be polarised**, which is the classic proof that light is transverse.



**Q. [PYQ] [NUMERICAL] A body of mass 4.9 kg hangs from a spring and oscillates with period 0.6 s. How much will the spring shorten when the body is removed?**

- (a) 0.809 metre
- (b) 1.089 metre
- (c) 1.009 metre
- (d) **0.089 metre  <-- CORRECT**

> **Why:** From T = 2pi sqrt(m/k) we get m/k = T^2/(4pi^2), and the static extension x = (m/k)g = **gT^2/(4pi^2)** = 9.8 x 0.36 / 39.478 = **0.089 m**. Note the **mass cancels out entirely** - it is a red herring, because a heavier mass stretches more but also oscillates more slowly.



**Q. [PYQ] [NUMERICAL] Two identical cells of emf 1.5 V and internal resistance 0.5 ohm are in series. If the permitted current is 1 A, the effective terminal potential difference is:**

- (a) 1 V
- (b) 0.75 V
- (c) **2 V  <-- CORRECT**
- (d) 0.5 V

> **Why:** In **series**, emf adds and internal resistance adds: EMF = 3 V, r = 1 ohm. Then **V = EMF - Ir** = 3 - (1)(1) = **2 V**. (In parallel, emf stays the same and r becomes r/n.)



**Q. [PYQ] The magnetic moment of a bar magnet is _____ the magnetic moment of an equivalent solenoid if the solenoid's magnetic field is _______ that of the bar magnet.**

- (a) **equal to ; same as  <-- CORRECT**
- (b) more than ; same as
- (c) less than ; same as
- (d) equal to ; different from

> **Why:** Definitional: an "**equivalent** solenoid" is one reproducing the magnet's behaviour. Since a dipole's external field is determined entirely by its magnetic moment, **same field implies equal magnetic moment**.



## 10.5 Accountancy and Business Economics



> **WEIGHTAGE: 3-5 marks in DSSSB only | Priority LOW for KVS/NVS**



### 10.5.1 Questions



**Q. [PYQ] According to the double entry system, every transaction will have ______ entries.**

- (a) Right and Left
- (b) Up and Down
- (c) **Debt and Credit  <-- CORRECT**
- (d) Up and Left

> **Why:** Every transaction has a **debit** side and a **credit** side of equal value (the paper spelled it "Debt"). Total debits always equal total credits, which is what a **trial balance** checks.



**Q. [PYQ] Which of the following accounts is/are prepared for net profit?**

- (a) **Profit and loss account  <-- CORRECT**
- (b) Trading account, profit and loss account and balance sheet
- (c) Trading account
- (d) Balance sheet

> **Why:** **Trading account gives GROSS profit; Profit and Loss account gives NET profit; Balance sheet shows position, not profit.** Keep the pair straight: Trading = Gross, P&L = Net.



**Q. [PYQ] What is a long-term asset in accounting?**

- (a) Intangible assets
- (b) Current liabilities
- (c) Fixed liabilities
- (d) **Fixed assets  <-- CORRECT**

> **Why:** **Fixed assets** are held for use in the business for more than one year and not for resale - land, building, machinery, vehicles. **Current assets** convert to cash within a year.



**Q. [PYQ] Any account or goods used by the owner of the business for his personal use is called:**

- (a) sales
- (b) **drawings  <-- CORRECT**
- (c) general expenses
- (d) expenses

> **Why:** **Drawings** reduce the owner's capital. Remember the accounting equation: **Assets = Liabilities + Capital**.



**Q. [PYQ] The part of the firm's capital required for conducting day-to-day expenses is called:**

- (a) **working capital  <-- CORRECT**
- (b) asset
- (c) expenses
- (d) fixed capital

> **Why:** "**Day to day**" is the trigger. **Working Capital = Current Assets - Current Liabilities**; long-term needs are met by **fixed** capital.



**Q. [PYQ] [NUMERICAL] [TRAP] ABC Ltd's purchases were Rs. 1,90,000. Gross profit was 20% ON SALES and closing stock was Rs. 30,000 more than opening stock. Find the gross profit.**

- (a) Rs. 35,000
- (b) Rs. 52,000
- (c) Rs. 25,000
- (d) **Rs. 40,000  <-- CORRECT**

> **Why:** Step 1: COGS = Opening + Purchases - Closing = 1,90,000 - 30,000 = **1,60,000** (the opening stock cancels out, so its value was never needed). Step 2: gross profit is 20% **of sales**, so COGS = 80% of sales, giving sales = 1,60,000/0.8 = **2,00,000**. Step 3: GP = 20% of 2,00,000 = **Rs. 40,000**. **The trap: "20% on sales" is NOT "20% on cost"** - on cost it would have been Rs. 32,000. Always check the base.



**Q. [PYQ] [NUMERICAL] Rent of Rs. 2,50,000 was received for the year ending 31 March 2024, of which Rs. 50,000 relates to next year. The amount credited to P&L is ____ and the advance is shown as ____.**

- (a) Rs. 1,50,000; Liability
- (b) Rs. 2,00,000; Asset
- (c) Rs. 3,00,000; Asset
- (d) **Rs. 2,00,000; Liability  <-- CORRECT**

> **Why:** Two principles. **Accrual concept**: only income *earned this year* goes to the P&L, so 2,50,000 - 50,000 = **2,00,000**. **Income received in advance**: the business still owes the service, and an obligation is a **LIABILITY**. The trap is marking it an asset because cash came in - the *cash* is an asset, but the unearned portion creates a matching liability.



**Q. [PYQ] A public company must have at least ______ members.**

- (a) 14
- (b) **7  <-- CORRECT**
- (c) 2
- (d) 3

> **Why:** Learn the pair: **private company minimum 2, public company minimum 7.** A **company** also has **limited liability** because it is a separate legal person, unlike a partnership or sole proprietorship.



**Q. [PYQ] The most common type of business organisation is:**

- (a) partnership
- (b) **sole proprietorship  <-- CORRECT**
- (c) NGO
- (d) corporation

> **Why:** Easiest and cheapest to start with no registration formalities, so it covers the vast majority of small shops and traders - despite carrying **unlimited liability**.



**Q. [PYQ] Which of the following is NOT a tertiary business activity?**

- (a) Transportation
- (b) Warehousing
- (c) Insurance
- (d) **Manufacturing  <-- CORRECT**

> **Why:** **Manufacturing is SECONDARY** (it physically makes goods). Transportation, warehousing and insurance are **auxiliaries to trade**, which defines tertiary/service activity. **Primary** = extraction from nature.



**Q. [PYQ] Which of the following statement is correct for a business organisation?**

- (a) Responsibility leads to decentralisation
- (b) Authority leads to decentralisation
- (c) **Delegation leads to decentralisation  <-- CORRECT**
- (d) Centralisation leads to autonomy

> **Why:** Systematic **delegation** of authority throughout the organisation **is** decentralisation. Note the last option states the exact opposite of the truth - it is *decentralisation* that gives autonomy. Also: authority can be delegated, but **accountability cannot**.



**Q. [PYQ] An organisation structure establishes relationships between:**

- (a) **people, work and resources  <-- CORRECT**
- (b) organisations and environment
- (c) suppliers and customers
- (d) organisations and society

> **Why:** Structure defines who does what work with which resources, and who reports to whom.



**Q. [PYQ] Elasticity of demand explains the ______ of the correlation between price and quantity.**

- (a) level, degree and angle
- (b) angle
- (c) level
- (d) **degree  <-- CORRECT**

> **Why:** Elasticity measures **magnitude of responsiveness**, so "degree" is the right word. Ed = (% change in quantity) / (% change in price).



**Q. [PYQ] Marginal revenue is calculated by:**

- (a) dividing the change in total output quantity by the change in total revenue
- (b) dividing the change in total cost by the change in total output quantity
- (c) **dividing the change in total revenue by the change in total output quantity  <-- CORRECT**
- (d) dividing the change in total revenue by the change in total profit

> **Why:** **MR = change in Total Revenue / change in Output.** Revenue on top, quantity below. The total-*cost* version defines **marginal cost** instead.



**Q. [PYQ] [TRAP] Which of the following inflations describes how demand for goods and services can drive up their prices?**

- (a) Cost-push inflation
- (b) Built-in Inflation
- (c) **Demand-pull inflation  <-- CORRECT**
- (d) Demand-push inflation

> **Why:** **Demand PULLS prices up; costs PUSH them up.** "Demand-push" does not exist as a term - mixing the two words is the most common error.



**Q. [PYQ] ______ is also referred to as the Sales-Force-Composite method or the Collective Opinion Method.**

- (a) Consumer interview method
- (b) Substitute approach
- (c) Evolutionary approach
- (d) **Opinion survey  <-- CORRECT**

> **Why:** Both alternative names refer to collecting and combining the **opinions** of the firm's own sales staff in their territories.



**Q. [PYQ] According to business economics, the growth of an existing product is used to estimate the demand for a new product using:**

- (a) growth curve approach
- (b) vicarious approach
- (c) **substitute approach  <-- CORRECT**
- (d) opinion polling approach

> **Why:** The new product is assumed to **substitute** for the existing one, so the existing product's growth indicates its potential. For a brand-new product with no history, firms use the **evolutionary, substitute and vicarious** approaches together.



**Q. [PYQ] Which of the following is NOT a type of business?**

- (a) Experience driven
- (b) **Expense driven  <-- CORRECT**
- (c) Efficiency driven
- (d) Expert driven

> **Why:** The genuine categories are **experience-driven, efficiency-driven and expert-driven** - based on whether a firm competes through accumulated experience, operational efficiency or specialist expertise. No business is defined by its *expenses*.



**Q. [PYQ] What does the term 'bootstrapping' refer to in the context of starting a business?**

- (a) Raising funds through venture capitalists
- (b) **Self-funding the business using personal resources  <-- CORRECT**
- (c) Obtaining bank loans for initial capital
- (d) Crowdfunding through online platforms

> **Why:** The image is "pulling yourself up by your own bootstraps". All three distractors involve **external** money, which is exactly what bootstrapping avoids.



**Q. [PYQ] Which of the following comes under applied mathematics?**

- (a) Information processing
- (b) **Operations research  <-- CORRECT**
- (c) Management accounting
- (d) Organisation

> **Why:** **Operations Research** applies mathematical optimisation, queuing theory, simulation and game theory to real decision problems - universally classified as applied mathematics.

