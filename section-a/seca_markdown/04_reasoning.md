
---

# PART 5 - General Intelligence and Reasoning Ability

> *20 marks. The most scorable section in the entire paper - pure technique, a closed list of question types, and no facts to forget. Target 19-20.*



## 5.1 Why Reasoning Is Your Best Section



### 5.1.1 The closed-list property


General Awareness is infinite - a question can come from anywhere. Reasoning is the opposite: the question types are a **finite, closed list**, and DSSSB reuses them year after year. Once you can recognise all of them on sight and you know the method for each, there is nothing left to be surprised by.

The official DSSSB syllabus lists the reasoning content as: analogies, similarities, differences, space visualisation, problem solving, analysis, judgment, decision making, visual memory, discrimination, observation, relationship concepts, arithmetical reasoning, verbal and figure classification, and arithmetical number series.

That translates into the chapters below. Master these and 20 out of 20 is genuinely achievable.


| Chapter | Topic | Typical questions per paper |
|---|---|---|
| 5.2 | Series - number, letter, alphanumeric | 2-3 |
| 5.3 | Analogy | 1-2 |
| 5.4 | Classification (odd one out) | 1-2 |
| 5.5 | Coding-decoding | 1-2 |
| 5.6 | Blood relations | 1-2 |
| 5.7 | Direction and distance | 1-2 |
| 5.8 | Ranking, order and arrangement | 1-2 |
| 5.9 | Seating arrangement and puzzles | 1-2 |
| 5.10 | Syllogism | 1-2 |
| 5.11 | Venn diagrams | 1 |
| 5.12 | Clocks and calendars | 1 |
| 5.13 | Mathematical operations and inequality | 1 |
| 5.14 | Non-verbal: mirror, water, paper folding, figure series | 1-2 |
| 5.15 | Miscellaneous: dice, cubes, logical order, statement-conclusion | 1-2 |



## 5.2 Series



### 5.2.1 Number series - the six patterns


Almost every number series in these papers is one of six patterns. Test them in this order.


| Pattern | How to spot it | Example |
|---|---|---|
| Constant difference | Differences are equal | 3, 7, 11, 15, ... (+4 each) to **19** |
| Increasing / decreasing difference | Differences form their own series | 2, 4, 8, 14, 22 (+2, +4, +6, +8) to **32** |
| Multiplication / division | Ratio is constant | 3, 6, 12, 24 (x2) to **48** |
| Squares and cubes | Numbers near n^2 or n^3 | 1, 4, 9, 16, 25 to **36**; 1, 8, 27, 64 to **125** |
| Mixed / alternating | Two interleaved series | 2, 9, 4, 11, 6, 13 (odd positions +2, even positions +2) to **8** |
| Sum / Fibonacci type | Each term = sum of previous two | 1, 1, 2, 3, 5, 8 to **13** |



*THE METHOD - follow this order every time*
```
Step 1: Write the DIFFERENCES between consecutive terms underneath.
Step 2: Are they constant?            -> arithmetic series, done.
Step 3: Do the differences form a pattern (2,4,6,8 / squares)? -> done.
Step 4: Not working? Try RATIOS instead (divide each term by the previous).
Step 5: Still nothing? Check for squares/cubes NEAR each term
        (e.g. 24 is 25-1, 26 is 25+1, 63 is 64-1).
Step 6: Still nothing? Suspect an ALTERNATING series - look at
        1st, 3rd, 5th terms as one series and 2nd, 4th, 6th as another.
Step 7: Last resort - check if each term is the sum or product of the
        two before it.
```



**Q. [PYQ-TYPE] Find the missing term: 5, 11, 23, 47, ?**

- (a) 71
- (b) 83
- (c) **95  <-- CORRECT**
- (d) 94

> **Why:** Differences are 6, 12, 24 - each doubling, so the next difference is 48, giving 47 + 48 = **95**. Alternative view: each term is (previous x 2) + 1, so 47 x 2 + 1 = 95. Both routes agree, which is a good sign.



**Q. [PYQ-TYPE] Find the next term: 2, 6, 12, 20, 30, ?**

- (a) 40
- (b) **42  <-- CORRECT**
- (c) 36
- (d) 44

> **Why:** Differences are 4, 6, 8, 10, so the next is 12, giving 30 + 12 = **42**. Note the elegant alternative: the terms are 1x2, 2x3, 3x4, 4x5, 5x6, so the next is **6x7 = 42**. Recognising the n(n+1) form is faster.



**Q. [EXPECTED] Find the missing term: 4, 9, 25, 49, ?, 169**

- (a) 100
- (b) **121  <-- CORRECT**
- (c) 144
- (d) 81

> **Why:** These are squares of **prime numbers**: 2^2, 3^2, 5^2, 7^2, **11^2 = 121**, 13^2. Whenever a square series skips awkwardly, check whether the roots are primes.



**Q. [EXPECTED] [TRAP] Find the odd term: 8, 27, 64, 100, 125**

- (a) 27
- (b) 64
- (c) **100  <-- CORRECT**
- (d) 125

> **Why:** The series is cubes: 2^3, 3^3, 4^3, 5^3. **100 is a square (10^2), not a cube**, so it breaks the pattern. Learn cubes to 10: 1, 8, 27, 64, 125, 216, 343, 512, 729, 1000.



**Q. [EXPECTED] Find the next term: 1, 3, 4, 7, 11, 18, ?**

- (a) 25
- (b) 27
- (c) **29  <-- CORRECT**
- (d) 31

> **Why:** Each term is the **sum of the two preceding terms**: 11 + 18 = **29**. This is a Fibonacci-type series with different seeds. Always test this if differences and ratios both fail.



### 5.2.2 Letter series - the position trick


Never count letters on your fingers. Memorise the alphabet positions and the series becomes arithmetic.


*Alphabet positions - learn these anchor points*
```
A  B  C  D  E  F  G  H  I  J  K  L  M
1  2  3  4  5  6  7  8  9 10 11 12 13

N  O  P  Q  R  S  T  U  V  W  X  Y  Z
14 15 16 17 18 19 20 21 22 23 24 25 26

ANCHORS to memorise:  E=5,  J=10,  O=15,  T=20,  Y=25
Mnemonic: "EJOTY"  -  five letters, five multiples of five.

REVERSE POSITION of any letter = 27 - (its position).
   So the reverse position of D (4) is 27 - 4 = 23, which is W.
```



> **TIP: The EJOTY shortcut in action**
>
> To find the position of R: the nearest anchor is O = 15, and R is three letters after O, so R = 18. To find the 22nd letter: T = 20, so 22 is two after T, which is V. This takes two seconds and never goes wrong.



**Q. [PYQ-TYPE] Complete the series: B, D, G, K, ?**

- (a) N
- (b) O
- (c) **P  <-- CORRECT**
- (d) Q

> **Why:** Convert to positions: B=2, D=4, G=7, K=11. Differences are +2, +3, +4, so the next is +5, giving 11 + 5 = 16 = **P**. Always convert letters to numbers first.



**Q. [PYQ-TYPE] Complete the series: AZ, BY, CX, ?**

- (a) DV
- (b) **DW  <-- CORRECT**
- (c) EW
- (d) DX

> **Why:** Two independent series. The first letters go A, B, C, so next is **D**. The second letters go Z, Y, X, so next is **W**. Answer **DW**. Note that in each pair the positions sum to 27 (A+Z = 1+26), which is a useful check.



**Q. [EXPECTED] Complete the series: AC, FH, KM, PR, ?**

- (a) TV
- (b) **UW  <-- CORRECT**
- (c) VX
- (d) TU

> **Why:** First letters: A(1), F(6), K(11), P(16), next **U(21)** - increasing by 5. Second letters: C(3), H(8), M(13), R(18), next **W(23)** - also by 5. Answer **UW**.



**Q. [EXPECTED] If the alphabet is written in reverse order, which letter is 7th from the left?**

- (a) G
- (b) **T  <-- CORRECT**
- (c) U
- (d) S

> **Why:** Reversed, the alphabet starts Z, Y, X, W, V, U, **T**. Alternatively use the formula: the 7th from the left in reverse = the 7th from the right in normal order = position 27 - 7 = 20 = **T**.



### 5.2.3 Alphanumeric and mixed series


These combine letters, numbers and sometimes symbols. Treat each stream separately.


**Q. [EXPECTED] Complete the series: A1, C4, E9, G16, ?**

- (a) H25
- (b) **I25  <-- CORRECT**
- (c) I20
- (d) J25

> **Why:** Letters: A, C, E, G - alternate letters, so next is **I**. Numbers: 1, 4, 9, 16 - perfect squares, so next is **25**. Answer **I25**.



## 5.3 Analogy



### 5.3.1 The method


An analogy asks you to find the **relationship** in the first pair and apply the identical relationship to the second. The discipline is to **state the relationship in words** before looking at the options.


| Relationship type | Example |
|---|---|
| Synonym | Happy : Joyful |
| Antonym | Hot : Cold |
| Part to whole | Wheel : Car |
| Whole to part | Book : Chapter |
| Cause and effect | Virus : Disease |
| Worker and tool | Carpenter : Saw |
| Worker and workplace | Doctor : Hospital |
| Product and raw material | Cloth : Cotton |
| Animal and young | Cow : Calf |
| Animal and home | Bee : Hive |
| Symbol and institution | Crown : Monarchy |
| Instrument and measurement | Thermometer : Temperature |
| Study and subject | Ornithology : Birds |



**Q. [PYQ-TYPE] Doctor : Stethoscope :: Carpenter : ?**

- (a) Wood
- (b) Furniture
- (c) **Chisel  <-- CORRECT**
- (d) Workshop

> **Why:** The relationship is **professional : the tool he uses**. A doctor uses a stethoscope; a carpenter uses a chisel. Note the traps: "wood" is the raw *material*, "furniture" is the *product*, and "workshop" is the *workplace* - all real relationships, but not the one in the first pair.



**Q. [PYQ-TYPE] Ornithology : Birds :: Entomology : ?**

- (a) Plants
- (b) Reptiles
- (c) **Insects  <-- CORRECT**
- (d) Fish

> **Why:** The relationship is **branch of study : what it studies**. Learn this family: **Ornithology** birds, **Entomology** insects, **Ichthyology** fish, **Herpetology** reptiles and amphibians, **Botany** plants, **Cardiology** heart, **Nephrology** kidneys, **Seismology** earthquakes, **Numismatics** coins, **Philately** stamps.



**Q. [EXPECTED] [NUMERICAL] 6 : 42 :: 9 : ?**

- (a) 72
- (b) 81
- (c) **90  <-- CORRECT**
- (d) 99

> **Why:** Find the rule: 6 x 7 = 42, i.e. n x (n+1). So 9 x 10 = **90**. Always test n^2 + n, n^2 - n, n^2 + 1 and n x (n+1) on numerical analogies.



**Q. [EXPECTED] Light : Blind :: Sound : ?**

- (a) Dumb
- (b) Noise
- (c) **Deaf  <-- CORRECT**
- (d) Silent

> **Why:** The relationship is **the sense stimulus : the person who cannot perceive it**. One who cannot perceive light is blind; one who cannot perceive sound is **deaf**. The trap "dumb" refers to inability to *speak*, not to hear.



## 5.4 Classification (Odd One Out)



### 5.4.1 The method


Find the property shared by three of the four items. The one lacking it is the answer. Check properties in this order: **category, then origin, then a numerical property, then spelling or letter structure**.


**Q. [PYQ-TYPE] Find the odd one out.**

- (a) Rose
- (b) Lotus
- (c) Jasmine
- (d) **Mango  <-- CORRECT**

> **Why:** Rose, lotus and jasmine are **flowers**; mango is a **fruit**. Always identify the category first.



**Q. [PYQ-TYPE] [TRAP] Find the odd one out.**

- (a) 27
- (b) 64
- (c) **100  <-- CORRECT**
- (d) 125

> **Why:** 27, 64 and 125 are perfect **cubes** (3^3, 4^3, 5^3); 100 is a perfect **square**. Note it is *also* the only one that is not a cube of a prime-or-small integer - but "not a cube" is the cleanest reason.



**Q. [EXPECTED] Find the odd one out.**

- (a) Copper
- (b) Silver
- (c) **Bronze  <-- CORRECT**
- (d) Gold

> **Why:** Copper, silver and gold are **elements** (pure metals); **bronze is an alloy** (copper + tin). This element-versus-alloy distinction is a favourite. Other common alloys: brass (copper + zinc), steel (iron + carbon), solder (lead + tin).



**Q. [EXPECTED] Find the odd one out.**

- (a) Cricket
- (b) Hockey
- (c) Football
- (d) **Chess  <-- CORRECT**

> **Why:** Cricket, hockey and football are **outdoor team games played on a field**; chess is an **indoor board game**. If a sports question appears, check indoor/outdoor and team/individual.



**Q. [EXPECTED] Find the odd one out.**

- (a) Nile
- (b) Amazon
- (c) **Sahara  <-- CORRECT**
- (d) Ganga

> **Why:** Nile, Amazon and Ganga are **rivers**; the Sahara is a **desert**.



## 5.5 Coding-Decoding



### 5.5.1 The four types



| Type | What happens | Example |
|---|---|---|
| Letter shifting | Each letter moves forward or backward by a fixed number | CAT with +1 becomes DBU |
| Letter reversal | Each letter is replaced by its opposite (A-Z, B-Y) | CAT becomes XZG |
| Number coding | Letters are replaced by their positions | CAT becomes 3-1-20 |
| Substitution / condition coding | Words or symbols stand for other words | "sky is blue" means "pa ta na" |



*THE METHOD*
```
Step 1: Write the code word directly UNDER the original word,
        letter by letter.
Step 2: Convert both to positions using EJOTY.
Step 3: Subtract to get the shift for each letter.
Step 4: Is the shift constant? Apply it to the new word.
        Is the shift a pattern (+1, +2, +3)? Continue the pattern.
Step 5: Check for reversal: does position(code) = 27 - position(original)?
```



**Q. [PYQ-TYPE] If TEACHER is coded as UFBDIFS, how is STUDENT coded?**

- (a) TUVEFOU
- (b) **TUVEFOU  <-- CORRECT**
- (c) STUDENT
- (d) TVUEFOU

> **Why:** Compare T to U, E to F, A to B: every letter moves **+1**. Applying +1 to STUDENT: S to T, T to U, U to V, D to E, E to F, N to O, T to U, giving **TUVEFOU**.



**Q. [PYQ-TYPE] If CAT is coded as XZG, how is DOG coded?**

- (a) WLT
- (b) **WLT  <-- CORRECT**
- (c) XLT
- (d) WMT

> **Why:** Check for reversal: C(3) becomes X(24), and 27 - 3 = 24. Yes, it is the **reverse-alphabet code**. So D(4) becomes 27-4 = 23 = W; O(15) becomes 27-15 = 12 = L; G(7) becomes 27-7 = 20 = T. Answer **WLT**.



**Q. [EXPECTED] [TRAP] In a certain code, MONKEY is written as XDJMNL. How is TIGER written?**

- (a) QDFHS
- (b) **QDFHS  <-- CORRECT**
- (c) SDFHQ
- (d) QFDHS

> **Why:** Look carefully - the code is **reversed AND each letter shifted by -1**. MONKEY reversed is YEKNOM; then each letter -1 gives XDJMNL. Correct. So TIGER reversed is REGIT; each letter -1 gives **QDFHS**. When a simple shift fails, always test whether the word has been reversed first.



**Q. [EXPECTED] If in a code 'pen' is 'table', 'table' is 'chair', 'chair' is 'book', what do you write on?**

- (a) Table
- (b) Chair
- (c) **Book  <-- CORRECT**
- (d) Pen

> **Why:** You write on a **chair**... in the coded language. The real object you write on is a *table*, and in this code "table" is called **"chair"**. Wait - read again: we need the coded name of the thing you actually write on. You write on a **table**, and table is called **chair**. Hmm - but the question as set expects the substitution chain. Careful method: write the mapping, then answer in the *coded* language. Real answer for "what do you write on" = table = coded as **chair**. This question type is deliberately confusing; **always write the mapping table out**.



> **NOTE: Read that last one again - it teaches the real lesson**
>
> Substitution-coding questions are designed to make you answer in the wrong language. The discipline that saves you:
>
> **Step 1.** Write the mapping in two columns - real name on the left, coded name on the right.
> **Step 2.** Answer the question in the **real** world first ("you write on a table").
> **Step 3.** Then translate that answer into the **coded** language using your table.
>
> Skipping step 2 is how candidates lose these marks.



## 5.6 Blood Relations



### 5.6.1 The symbol method


Never try to hold a family tree in your head. Draw it, using a fixed notation.


*Standard notation - use it every time*
```
   +  =  male            -  =  female
   Horizontal line with a double dash  =  married couple
   Vertical line downward               =  parent to child
   Horizontal line under a couple       =  siblings

Example: "A is the father of B, B is the sister of C"

        A(+)
          |
      +---+---+
      |       |
     B(-)    C(?)

   B is female (sister), C's gender is unknown.
```



| Relationship | Meaning |
|---|---|
| Paternal | Father's side (father's brother is your uncle, father's sister is your aunt) |
| Maternal | Mother's side (mother's brother is your maternal uncle) |
| Sibling | Brother or sister |
| Only child | Has no brothers or sisters |
| Spouse | Husband or wife |
| In-law | Related by marriage - father-in-law, sister-in-law |
| First cousin | Child of your uncle or aunt |
| Nephew / Niece | Son / daughter of your sibling |



**Q. [PYQ-TYPE] Pointing to a photograph, a man said, "She is the daughter of my grandfather's only son." How is she related to him?**

- (a) Mother
- (b) Aunt
- (c) **Sister  <-- CORRECT**
- (d) Cousin

> **Why:** Work inward. "My grandfather's only son" - since the grandfather has only one son, and that son must be the speaker's father, this phrase means **my father**. So she is "the daughter of my father" = his **sister**.



**Q. [PYQ-TYPE] A is the brother of B. C is the mother of B. D is the father of C. How is A related to D?**

- (a) Son
- (b) Father
- (c) Grandfather
- (d) **Grandson  <-- CORRECT**

> **Why:** D is C's father; C is B's mother, and A is B's brother, so C is also A's mother. Therefore D is A's mother's father = A's **grandfather**, which makes A the **grandson** of D. Note the question asks how **A relates to D**, not the reverse - a very common careless error.



**Q. [EXPECTED] [TRAP] Introducing a man, a woman said, "His wife is the only daughter of my father." How is the man related to the woman?**

- (a) Brother
- (b) Father
- (c) **Husband  <-- CORRECT**
- (d) Uncle

> **Why:** "The only daughter of my father" is the **woman herself**. So the man's wife is this woman, which makes the man her **husband**. The trap is answering "brother" by pattern-matching on "my father" without noticing that the phrase refers back to the speaker.



**Q. [EXPECTED] P is the sister of Q. R is the father of Q. S is the brother of R. How is S related to P?**

- (a) Father
- (b) Brother
- (c) **Uncle  <-- CORRECT**
- (d) Grandfather

> **Why:** R is P's father (since R is Q's father and P is Q's sister). S is R's brother, so S is the brother of P's father = P's **uncle** (paternal).



## 5.7 Direction and Distance



### 5.7.1 The method


Always draw. Fix north at the top of your rough sheet before you read the question.


*Direction basics*
```
                    NORTH
                      |
        NORTH-WEST    |    NORTH-EAST
                      |
   WEST -------------- + -------------- EAST
                      |
        SOUTH-WEST    |    SOUTH-EAST
                      |
                    SOUTH

TURNS:
   Right turn  = 90 degrees clockwise
   Left turn   = 90 degrees anticlockwise
   About turn / U-turn = 180 degrees

FACING NORTH: right hand points EAST, left hand points WEST.
FACING SOUTH: right hand points WEST, left hand points EAST.  (reversed!)
FACING EAST : right hand points SOUTH, left hand points NORTH.
FACING WEST : right hand points NORTH, left hand points SOUTH.
```


- **Shortest distance** - When the path forms a right angle, the shortest distance is the **hypotenuse**: sqrt(a^2 + b^2). Memorise the common Pythagorean triples: **3-4-5, 5-12-13, 8-15-17, 7-24-25, 9-40-41**.


**Q. [PYQ-TYPE] [NUMERICAL] A man walks 4 km north, then 3 km east. How far is he from the starting point?**

- (a) 7 km
- (b) **5 km  <-- CORRECT**
- (c) 1 km
- (d) 12 km

> **Why:** North and east are perpendicular, so the displacement is the hypotenuse: sqrt(4^2 + 3^2) = sqrt(16+9) = sqrt25 = **5 km**. This is the 3-4-5 triple - recognise it instantly.



**Q. [PYQ-TYPE] [NUMERICAL] Ravi walks 10 m south, turns left and walks 5 m, turns left and walks 10 m. Which direction is he facing and how far from the start?**

- (a) North, 5 m
- (b) **North, 5 m east of start  <-- CORRECT**
- (c) South, 5 m
- (d) East, 10 m

> **Why:** Facing south, a **left turn points him east**, so he walks 5 m east. Facing east, a left turn points him **north**, and he walks 10 m north - which exactly cancels the original 10 m south. So he ends up **5 m east of the start, facing north**. The key skill is getting the left/right turn correct when facing south.



**Q. [EXPECTED] [TRAP] A person facing south turns 90 degrees clockwise, then 180 degrees, then 90 degrees anticlockwise. Which direction is he facing?**

- (a) South
- (b) East
- (c) **North  <-- CORRECT**
- (d) West

> **Why:** Facing south, 90 clockwise gives **west**. Then 180 gives **east**. Then 90 anticlockwise from east gives **north**. Draw each step - do not do this in your head.



**Q. [EXPECTED] [NUMERICAL] A man goes 5 km east, 12 km north. Find the shortest distance from the start.**

- (a) 17 km
- (b) **13 km  <-- CORRECT**
- (c) 7 km
- (d) 15 km

> **Why:** sqrt(25 + 144) = sqrt169 = **13 km** - the 5-12-13 triple.



## 5.8 Ranking, Order and Arrangement



### 5.8.1 The two formulas that solve almost everything



*[FORMULA] Ranking formulas*
```
1. Total number of persons
      = (rank from top) + (rank from bottom) - 1

   Why the -1? Because the person himself is counted in BOTH ranks.

2. Number of persons between two people
      = (difference of their positions from the same end) - 1

3. If rank from top is r in a group of n,
      rank from bottom = n - r + 1
```



**Q. [PYQ-TYPE] [NUMERICAL] In a class, Amit is 12th from the top and 18th from the bottom. How many students are in the class?**

- (a) 30
- (b) **29  <-- CORRECT**
- (c) 31
- (d) 28

> **Why:** Total = 12 + 18 - 1 = **29**. The -1 is essential because Amit is counted in both the 12 and the 18. Forgetting it is the single most common error in this topic.



**Q. [PYQ-TYPE] [NUMERICAL] In a row of 40 children, Rahul is 15th from the left. What is his position from the right?**

- (a) 25th
- (b) **26th  <-- CORRECT**
- (c) 24th
- (d) 27th

> **Why:** Position from right = 40 - 15 + 1 = **26th**. Sanity check: 15 + 26 - 1 = 40. Correct.



**Q. [EXPECTED] [NUMERICAL] [TRAP] In a row of 25 students, A is 10th from the left and B is 8th from the right. How many students are between them?**

- (a) 8
- (b) **7  <-- CORRECT**
- (c) 9
- (d) 6

> **Why:** Convert to a common end. B is 8th from the right, so from the left B is 25 - 8 + 1 = **18th**. A is 10th from the left. Students between = 18 - 10 - 1 = **7**. The trap is answering 8 by forgetting to subtract 1 for the gap rather than the span.



**Q. [EXPECTED] [NUMERICAL] Five friends are of different heights. A is taller than B but shorter than C. D is taller than C. E is the shortest. Who is the tallest?**

- (a) A
- (b) C
- (c) **D  <-- CORRECT**
- (d) B

> **Why:** Build the chain: E < B < A < C < D. So **D** is tallest. Write inequalities in one direction only - mixing "taller than" and "shorter than" in the same chain is how candidates go wrong.



## 5.9 Seating Arrangement and Puzzles



### 5.9.1 The method that makes puzzles solvable



*THE PUZZLE METHOD*
```
Step 1: Read ALL statements once without writing anything, to learn
        the shape of the problem (a row? a circle? facing in or out?).

Step 2: Draw the frame - the correct number of seats in the correct shape.

Step 3: Start with the MOST DEFINITE statement, never the first one.
        "C sits at the extreme left" is definite.
        "A sits near B" is not - leave it for later.

Step 4: Enter only what is certain. Use pencil for possibilities.

Step 5: Use ELIMINATION on the remaining statements.

Step 6: Re-read every statement at the end to VERIFY your final
        arrangement satisfies all of them.
```



| Arrangement type | Critical rule |
|---|---|
| Linear row, all facing north | Your left is the arrangement's left. Left and right work normally |
| Linear row, all facing south | **Left and right are REVERSED** relative to your page |
| Circle, all facing centre | **Clockwise appears anticlockwise** to you. Immediate left of a person is your right |
| Circle, all facing outward | Directions are as you see them |
| Two rows facing each other | A person in row 1 faces a person in row 2; their left/right are opposite |



> **TIP: The single most common puzzle error**
>
> When people face the **centre of a circle**, their left hand points **clockwise** as drawn on your page. When they face **outward**, their left hand points anticlockwise. Getting this backwards invalidates the entire arrangement. Write "facing centre = left is clockwise" at the top of your rough sheet before you start.



**Q. [PYQ-TYPE] Five people A, B, C, D, E sit in a row facing north. C is at the extreme right. A is second from the left. B is immediately left of C. D is not at either end. Who is at the extreme left?**

- (a) A
- (b) B
- (c) D
- (d) **E  <-- CORRECT**

> **Why:** Start definite: C is at position 5. B is immediately left of C, so B is at 4. A is at position 2. D is not at an end, so D cannot be at 1, leaving D at 3. That leaves position 1 for **E**.



**Q. [EXPECTED] Six friends sit around a circular table facing the centre. P is second to the right of Q. R is between S and T. U is not adjacent to Q. If S is immediately right of P, who is opposite Q?**

- (a) P
- (b) R
- (c) S
- (d) **T  <-- CORRECT**

> **Why:** Fix Q, place P two seats to Q's right (clockwise). S immediately right of P. R between S and T, so T follows. U takes the remaining seat, and check U is not adjacent to Q. Working the circle through gives **T** opposite Q. Draw a hexagon and fill it - never attempt circular puzzles mentally.



## 5.10 Syllogism



### 5.10.1 The rules


A syllogism gives you statements you must **accept as true even if absurd**, then asks which conclusions definitely follow.


*THE VENN DIAGRAM METHOD - the only reliable way*
```
Step 1: Draw the statements as circles.
        "All A are B"      -> circle A entirely INSIDE circle B
        "Some A are B"      -> circles A and B OVERLAP
        "No A is B"         -> circles A and B are SEPARATE
        "Some A are not B"  -> part of A lies outside B

Step 2: For each conclusion, ask: is it true in EVERY possible
        diagram consistent with the statements?
        Yes  -> it follows.
        No (you can draw even ONE diagram where it fails) -> it does not follow.
```



| [FORMULA] Valid inference rules | Result |
|---|---|
| All A are B + All B are C | **All A are C** follows |
| All A are B + Some B are C | **Nothing** definite follows |
| Some A are B + All B are C | **Some A are C** follows |
| No A is B + All C are B | **No C is A** follows |
| Some A are B | **Some B are A** always follows (conversion of "some" is valid) |
| All A are B | **Some B are A** follows, but "All B are A" does **NOT** |
| No A is B | **No B is A** follows |



**Q. [PYQ-TYPE] Statements: All roses are flowers. All flowers are plants. Conclusions: I. All roses are plants. II. All plants are roses.**

- (a) Only II follows
- (b) **Only I follows  <-- CORRECT**
- (c) Both follow
- (d) Neither follows

> **Why:** Roses sit inside flowers, which sit inside plants - so **all roses are plants** definitely follows. But plants is the largest circle and may contain much besides roses, so "all plants are roses" does **not** follow. **Rule: "All" never reverses.**



**Q. [PYQ-TYPE] [TRAP] Statements: Some books are pens. All pens are pencils. Conclusions: I. Some books are pencils. II. All books are pencils.**

- (a) Both follow
- (b) **Only I follows  <-- CORRECT**
- (c) Only II follows
- (d) Neither follows

> **Why:** The books that are pens must also be pencils (since all pens are pencils), so **some books are pencils** follows. But nothing tells us about the books that are *not* pens, so "all books are pencils" does not follow. **"Some" + "All" gives "Some", never "All".**



**Q. [EXPECTED] Statements: No cat is a dog. All dogs are animals. Conclusions: I. No cat is an animal. II. Some animals are not cats.**

- (a) Only I follows
- (b) **Only II follows  <-- CORRECT**
- (c) Both follow
- (d) Neither follows

> **Why:** Dogs are animals and no dog is a cat, so there exist animals (the dogs) that are not cats - **conclusion II follows**. Conclusion I fails because cats could themselves be animals; the statements only separate cats from *dogs*, not from animals in general. Draw it: a large "animals" circle containing a "dogs" circle, with "cats" overlapping animals but not dogs.



## 5.11 Venn Diagrams



**Q. [PYQ-TYPE] Which diagram best represents the relationship between Doctors, Surgeons and Human beings?**

- (a) Three separate circles
- (b) Three overlapping circles
- (c) **Surgeons inside Doctors, both inside Human beings  <-- CORRECT**
- (d) Doctors inside Surgeons

> **Why:** All surgeons are doctors, and all doctors are human beings - so the relationship is **fully nested**: the smallest circle (Surgeons) inside Doctors, inside the largest circle (Human beings). Test nesting first on such questions.



**Q. [EXPECTED] Which represents Mother, Doctor, Woman?**

- (a) Three separate
- (b) **Mother and Doctor overlap, both inside Woman  <-- CORRECT**
- (c) Nested
- (d) Doctor inside Mother

> **Why:** A mother is necessarily a woman; a doctor here (given the third term) is a woman too. But a mother may or may not be a doctor, so **Mother and Doctor overlap** partially, and both lie **inside Woman**.



## 5.12 Clocks and Calendars



### 5.12.1 Clocks



*[FORMULA] Clock formulas*
```
The minute hand moves  360/60 = 6 degrees per minute.
The hour hand moves    360/12/60 = 0.5 degrees per minute.
So the minute hand gains 5.5 degrees per minute on the hour hand.

ANGLE between the hands at H hours M minutes:
        Angle = | 30H - 5.5M |
   (If the result exceeds 180, subtract it from 360.)

The hands COINCIDE 11 times in 12 hours (22 times a day).
The hands are OPPOSITE 11 times in 12 hours (22 times a day).
The hands are at RIGHT ANGLES 22 times in 12 hours (44 times a day).
The hands coincide every 65 + 5/11 minutes.
```



**Q. [PYQ-TYPE] [NUMERICAL] What is the angle between the hands of a clock at 3:30?**

- (a) 90 degrees
- (b) **75 degrees  <-- CORRECT**
- (c) 85 degrees
- (d) 65 degrees

> **Why:** Angle = |30H - 5.5M| = |30(3) - 5.5(30)| = |90 - 165| = **75 degrees**. Note that the intuitive answer 90 is wrong, because by 3:30 the hour hand has moved halfway toward 4.



**Q. [EXPECTED] [NUMERICAL] Find the angle between the hands at 9:20.**

- (a) 150 degrees
- (b) **160 degrees  <-- CORRECT**
- (c) 170 degrees
- (d) 140 degrees

> **Why:** |30(9) - 5.5(20)| = |270 - 110| = **160 degrees**. Since 160 is under 180, no adjustment is needed.



### 5.12.2 Calendars



*[FORMULA] Calendar rules*
```
ODD DAYS = the remainder when the number of days is divided by 7.

An ORDINARY year has 365 days = 52 weeks + 1 day  -> 1 odd day.
A LEAP year has    366 days = 52 weeks + 2 days  -> 2 odd days.

LEAP YEAR RULE: divisible by 4; but a century year must be
divisible by 400. So 1900 was NOT a leap year; 2000 WAS.

100 years  -> 5 odd days
200 years  -> 3 odd days
300 years  -> 1 odd day
400 years  -> 0 odd days

Day codes: 0 = Sunday, 1 = Monday, 2 = Tuesday, 3 = Wednesday,
           4 = Thursday, 5 = Friday, 6 = Saturday.
```



**Q. [PYQ-TYPE] [NUMERICAL] If 1 January 2024 is a Monday, what day is 1 January 2025?**

- (a) Monday
- (b) **Wednesday  <-- CORRECT**
- (c) Tuesday
- (d) Thursday

> **Why:** 2024 is a **leap year** (divisible by 4 and not a century), so it contributes **2 odd days**. Monday + 2 = **Wednesday**. Candidates lose this by assuming 1 odd day without checking for a leap year.



**Q. [EXPECTED] [NUMERICAL] [TRAP] Was 1900 a leap year?**

- (a) Yes, because it is divisible by 4
- (b) **No, because a century year must be divisible by 400  <-- CORRECT**
- (c) Yes, all century years are leap years
- (d) Cannot be determined

> **Why:** 1900 is divisible by 4 but it is a **century year**, and century years must be divisible by **400**. 1900/400 is not a whole number, so it was **not** a leap year. By contrast 2000/400 = 5, so 2000 was.



## 5.13 Mathematical Operations and Inequality



### 5.13.1 Symbol substitution and BODMAS


- **BODMAS** - **B**rackets, **O**rders (powers and roots), **D**ivision, **M**ultiplication, **A**ddition, **S**ubtraction. Division and multiplication rank equally and are done left to right; likewise addition and subtraction.


**Q. [PYQ-TYPE] [NUMERICAL] If '+' means divide, '-' means multiply, 'x' means subtract and '/' means add, then 12 + 6 - 3 x 4 / 8 = ?**

- (a) 6
- (b) **10  <-- CORRECT**
- (c) 8
- (d) 4

> **Why:** Substitute the real operations: 12 / 6 x 3 - 4 + 8. Now apply BODMAS: division and multiplication first, left to right - (12/6) = 2, then 2 x 3 = 6. Then 6 - 4 + 8 = **10**. **Substitute first, then apply BODMAS - never mix the two steps.**



**Q. [EXPECTED] [NUMERICAL] Which sign should replace the question mark? 36 ? 4 + 5 = 14**

- (a) +
- (b) -
- (c) x
- (d) **/  <-- CORRECT**

> **Why:** Test: 36 / 4 + 5 = 9 + 5 = **14**. Correct, so the answer is division.



### 5.13.2 Coded inequality



| Rule | Result |
|---|---|
| A > B and B > C | **A > C** definitely |
| A > B and B = C | **A > C** definitely |
| A > B and B >= C | **A > C** definitely |
| A >= B and B >= C | **A >= C** (not A > C) |
| A > B and C > B | **No relation** between A and C - both are merely bigger than B |



**Q. [EXPECTED] [TRAP] Statements: A > B, B >= C, C > D. Conclusions: I. A > D. II. B > D.**

- (a) Only I
- (b) Only II
- (c) **Both I and II  <-- CORRECT**
- (d) Neither

> **Why:** Chain them: A > B >= C > D. Since the chain runs in one direction with at least one strict inequality between each pair of endpoints, **A > D** holds and **B > D** holds (B >= C > D gives B > D). Both follow. The trap is thinking that a >= link breaks the strict conclusion - it does not, as long as one strict > appears in the chain.



## 5.14 Non-Verbal Reasoning



### 5.14.1 Mirror and water images



*Mirror image  -  LEFT and RIGHT are interchanged (vertical flip axis)*
```
Letters UNCHANGED in a mirror (when the mirror is vertical, beside the text):
        A  H  I  M  O  T  U  V  W  X  Y
   These are symmetric about a VERTICAL axis.

Water image  -  TOP and BOTTOM are interchanged (horizontal flip axis)
Letters UNCHANGED in water:
        B  C  D  E  H  I  K  O  X
   These are symmetric about a HORIZONTAL axis.

Numbers unchanged in water:  0  1  3  8
```



**Q. [PYQ-TYPE] Which letters remain unchanged in their mirror image?**

- (a) B, C, D
- (b) **A, H, I, M  <-- CORRECT**
- (c) E, F, G
- (d) P, Q, R

> **Why:** Mirror images preserve letters that are symmetric about a **vertical** axis: A, H, I, M, O, T, U, V, W, X, Y. B, C, D and E are symmetric about a *horizontal* axis, so they survive a **water** image instead - a classic swap in the options.



### 5.14.2 Paper folding and cutting


- **Method** - Work **backwards**. Start from the final cut shape and unfold one step at a time, mirroring the holes across each fold line. Each unfolding **doubles** the number of holes.
- **Key fact** - A paper folded n times and cut once produces **2^n** holes when opened, provided the cut does not lie on a fold line.


### 5.14.3 Figure series and analogy



| What to check | Question to ask |
|---|---|
| Rotation | Is the figure turning? By how much - 45, 90, 180 degrees? Clockwise or anticlockwise? |
| Reflection | Is it flipping across an axis? |
| Addition or removal of elements | Are lines, dots or shapes being added each step? |
| Movement | Is an element moving position by a fixed rule (one corner clockwise each step)? |
| Shading | Is the shading shifting or inverting? |
| Counting | Is the number of sides, lines or dots following a series? |



> **TIP: The order to check figure series**
>
> Check in this sequence: **rotation, then movement of a marker, then addition/subtraction of elements, then shading**. Roughly 70% of figure series in these papers are simple rotation or a marker moving one position per step.



## 5.15 Miscellaneous Types



### 5.15.1 Dice and cubes


- **Standard dice rule** - On a standard die, **opposite faces sum to 7**: 1-6, 2-5, 3-4.
- **Two views of a die** - If two faces are **common** to both views, the remaining two faces are opposite each other.
- **Painted cube** - A cube painted on all sides and cut into n^3 smaller cubes gives: **8** cubes with 3 painted faces (the corners), **12(n-2)** with 2 faces (the edges), **6(n-2)^2** with 1 face (the centres), and **(n-2)^3** with **0** painted faces (the interior).


**Q. [EXPECTED] [NUMERICAL] A cube painted on all faces is cut into 27 equal smaller cubes. How many have no face painted?**

- (a) 8
- (b) 4
- (c) **1  <-- CORRECT**
- (d) 6

> **Why:** Here n = 3, so cubes with no painted face = (n-2)^3 = 1^3 = **1** - only the very centre cube. Check the rest: corners 8, edges 12(1) = 12, faces 6(1) = 6, interior 1. Total 8+12+6+1 = 27. Correct.



### 5.15.2 Logical order of words


Arrange in a natural sequence - by size, by time, by process order, or by hierarchy.


**Q. [PYQ-TYPE] Arrange in a logical order: stomach, mouth, food pipe, large intestine, small intestine**

- (a) **mouth, food pipe, stomach, small intestine, large intestine  <-- CORRECT**
- (b) mouth, stomach, food pipe, small intestine, large intestine
- (c) food pipe, mouth, stomach, large intestine, small intestine
- (d) mouth, food pipe, stomach, large intestine, small intestine

> **Why:** Follow the actual path of food through the digestive system: **mouth, food pipe (oesophagus), stomach, small intestine, large intestine**. Note the last two - the **small** intestine comes before the large one, which is the point of the question.



**Q. [EXPECTED] Arrange in logical order: seed, plant, flower, fruit, tree**

- (a) **seed, plant, tree, flower, fruit  <-- CORRECT**
- (b) seed, plant, flower, fruit, tree
- (c) plant, seed, tree, flower, fruit
- (d) seed, tree, plant, flower, fruit

> **Why:** The developmental sequence is seed, then a young plant, which grows into a tree, which bears flowers, which become fruit: **seed, plant, tree, flower, fruit**.



### 5.15.3 Statement and conclusion / assumption


- **Statement-Conclusion** - Accept the statement as true. A conclusion follows only if it is **necessarily** implied - not merely plausible or likely.
- **Statement-Assumption** - An assumption is something **taken for granted** for the statement to make sense. Test it by negation: if denying the assumption destroys the statement, it is a valid assumption.
- **Common trap** - Anything requiring **outside knowledge** or an extra leap is **not** a valid conclusion, however true it may be in reality.


**Q. [EXPECTED] [TRAP] Statement: "Use our shampoo for shining, healthy hair." Which assumption is implicit?**

- (a) All shampoos are harmful
- (b) **People want shining, healthy hair  <-- CORRECT**
- (c) No other shampoo works
- (d) Hair problems are common

> **Why:** The advertisement only makes sense if people **desire** shining, healthy hair - deny that and the whole message collapses, so it is the implicit assumption. The other options are far stronger claims the statement does not need. **The correct assumption is always the minimum needed, never the boldest.**



## 5.16 Reasoning Revision Sheet



### 5.16.1 Every formula in one place



*[FORMULA] The complete reasoning formula sheet*
```
ALPHABET
   EJOTY anchors:  E=5, J=10, O=15, T=20, Y=25
   Reverse position of a letter = 27 - (its position)

RANKING
   Total = (rank from top) + (rank from bottom) - 1
   Rank from bottom = Total - (rank from top) + 1
   Persons between = (difference of positions from same end) - 1

DIRECTIONS
   Shortest distance across a right angle = sqrt(a^2 + b^2)
   Triples: 3-4-5, 5-12-13, 8-15-17, 7-24-25, 9-40-41
   Facing SOUTH reverses left and right

CLOCK
   Angle = |30H - 5.5M|   (subtract from 360 if over 180)
   Minute hand 6 deg/min, hour hand 0.5 deg/min
   Hands coincide 22 times a day, opposite 22 times, right angle 44 times

CALENDAR
   Ordinary year = 1 odd day;  Leap year = 2 odd days
   Leap: divisible by 4, but century must be divisible by 400
   100 yr = 5 odd days, 200 = 3, 300 = 1, 400 = 0
   0=Sunday, 1=Monday, ... 6=Saturday

DICE AND CUBES
   Opposite faces of a standard die sum to 7
   Painted cube cut into n^3:
      3 faces painted = 8
      2 faces painted = 12(n-2)
      1 face painted  = 6(n-2)^2
      0 faces painted = (n-2)^3

MIRROR AND WATER
   Mirror-safe letters: A H I M O T U V W X Y
   Water-safe letters : B C D E H I K O X
   Water-safe digits  : 0 1 3 8

SYLLOGISM
   All + All   -> All
   Some + All  -> Some
   All + Some  -> nothing
   "Some" reverses;  "All" does NOT reverse
```



### 5.16.2 The five habits that produce 19-20 out of 20


1. **Convert letters to numbers immediately.** Every letter-series and coding question becomes arithmetic the moment you apply EJOTY.
2. **Draw, do not imagine.** Blood relations, directions, seating and syllogisms are all solved on paper. Candidates who attempt them mentally lose 4-5 marks per paper.
3. **Start puzzles from the most definite statement**, never from the first one.
4. **Verify at the end.** Once you have an arrangement, re-read every statement to confirm it fits. This catches almost every error before it costs you.
5. **Never exceed 2 minutes on one question.** Flag and return. A puzzle you cannot crack in 2 minutes is worth the same 1 mark as a synonym you can answer in 8 seconds.
