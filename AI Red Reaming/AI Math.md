## Basic Arithmetic Operations
*(These are the foundational actions computers take.)*

* **Multiplication (`*`):** Finds the **product**.
    * *Simple Meaning:* Scaling a value.
    * *Example:* `3 * 4 = 12`. If a model determines a certain feature is **3 times more important** than another, it multiplies its value by 3.
* **Division (`/`):** Splits a number.
    * *Simple Meaning:* Calculating a ratio or normalizing a value.
    * *Example:* `10 / 2 = 5`. If you calculate an average, you divide the sum by the count.
* **Addition (`+`):** Finds the **sum**.
    * *Simple Meaning:* Combining values.
    * *Example:* `5 + 3 = 8`. Used to combine weighted inputs in a neural network.
* **Subtraction (`-`):** Finds the **difference**.
    * *Simple Meaning:* Measuring how far apart two numbers are.
    * *Example:* `9 - 4 = 5`. Used to calculate the **error** (predicted value minus actual value).

---

## Algebraic Notations

* **Subscript Notation ($x_t$)**
    * *Simple Meaning:* An **ID tag** or index. It tells you *which* item in a list or sequence you're looking at.
    * *Example:* If $x$ is a list of temperatures taken every hour, $x_5$ is the temperature at hour 5. $x_{t-2}$ is the value two steps before the current time $t$.
* **Superscript Notation ($x^n$)**
    * *Simple Meaning:* An **exponent** or **power**.
    * *Example:* $x^2 = x * x$. Used extensively in calculating areas, volumes, and distances.
* **Norm ($||...||$)**
    * *Simple Meaning:* Measures the **size** or **length** of a vector (a list of numbers, like a data point). It's the distance from the origin.
    * *Euclidean Norm Calculation (L2):* This is the standard straight-line distance (like the Pythagorean theorem).
        $$\|v\| = \sqrt{v_1^2 + v_2^2}$$
        *Example:* For vector $v = [3, 4]$, the norm is $\sqrt{3^2 + 4^2} = \sqrt{9+16} = \sqrt{25} = 5$.
    * *L1 Norm (Manhattan):* Sums the absolute values. $||v||_1 = |3| + |4| = 7$.
    * *L$\infty$ Norm:* Takes the largest value. $||v||_{\infty} = \max(|3|, |4|) = 4$.
* **Summation Symbol ($\Sigma$)**
    * *Simple Meaning:* A compact way to say **"add up all these terms."**
    * *Example:* $\sum_{i=1}^{3} a_i$ means $a_1 + a_2 + a_3$. If $a = [10, 20, 30]$, the sum is $10+20+30=60$.

---

## Logarithms and Exponentials
*(These model growth and are fundamental to probability.)*

* **Logarithm Base 2 ($\log_2(x)$)**
    * *Simple Meaning:* Asks: "2 raised to **what power** equals $x$?"
    * *Example:* $\log_2(8) = 3$, because $2^3 = 8$. Used to measure information (bits).
* **Natural Logarithm ($\ln(x)$)**
    * *Simple Meaning:* Asks: "$e$ raised to **what power** equals $x$?" ($e \approx 2.718$ is a natural growth constant).
    * *Example:* $\ln(e^2) = 2$. Used widely in calculus because it models continuous change smoothly.
* **Exponential Function ($e^x$)**
    * *Simple Meaning:* $e$ multiplied by itself $x$ times. Models continuous **natural growth**.
    * *Example:* $e^2 \approx 7.389$. Used in the "Softmax" function to convert raw scores into probabilities.
* **Exponential Function (Base 2) ($2^x$)**
    * *Simple Meaning:* 2 multiplied by itself $x$ times.
    * *Example:* $2^3 = 8$. Key in computer science for binary representations.

---

## Matrix and Vector Operations
*(These are the mechanics of deep learning, allowing computers to process large data tables.)*

* **Matrix-Vector Multiplication ($A \times v$)**
    * *Simple Meaning:* Applying a **transformation** or **filter** to a single vector/data point.
    * *Example:* Matrix $A = [[1, 2], [3, 4]]$ acts on vector $v = [5, 6]$.
        * Result 1: $(1 \times 5) + (2 \times 6) = 17$
        * Result 2: $(3 \times 5) + (4 \times 6) = 39$
        * Final vector: $[17, 39]$. This is how input data is processed in a neural network layer.
* **Matrix-Matrix Multiplication ($A \times B$)**
    * *Simple Meaning:* Applying one transformation ($B$) followed by another ($A$), or processing an entire batch of vectors at once.
    * *Example:* $A = [[1, 2], [3, 4]]$, $B = [[5, 6], [7, 8]]$. The result is a new matrix. Used to combine weights between layers.
* **Transpose ($A^T$)**
    * *Simple Meaning:* **Flip the matrix** across its main diagonal (rows become columns and vice versa).
    * *Example:* If $A = [[1, 2], [3, 4]]$, then $A^T = [[1, 3], [2, 4]]$. Used to prepare matrices for multiplication.
* **Inverse ($A^{-1}$)**
    * *Simple Meaning:* The matrix that **undoes** the effect of $A$.
    * *Example:* If $A$ rotates an image 45 degrees, $A^{-1}$ rotates it back -45 degrees. Used to solve systems of linear equations.
* **Determinant ($\det(A)$)**
    * *Simple Meaning:* A **single number** calculated from a square matrix that tells you if the matrix is invertible (non-zero determinant) and how much the matrix scales space.
    * *Example:* For $A = [[1, 2], [3, 4]]$, $\det(A) = (1 \times 4) - (2 \times 3) = 4 - 6 = -2$.
* **Trace ($\text{tr}(A)$)**
    * *Simple Meaning:* The **sum of the elements on the main diagonal** (top-left to bottom-right).
    * *Example:* For $A = [[1, 2], [3, 4]]$, $\text{tr}(A) = 1 + 4 = 5$.

---

## Set Theory
*(Used for grouping, filtering, and counting data points.)*

* **Cardinality ($|S|$)**
    * *Simple Meaning:* The **count** of how many elements are in the set $S$.
    * *Example:* If $S = \{red, green, blue\}$, then $|S| = 3$.
* **Union ($\cup$)**
    * *Simple Meaning:* The set of **all unique elements** found in set A **OR** set B. (Logical OR).
    * *Example:* $A=\{1, 2\}, B=\{2, 3\}$. $A \cup B = \{1, 2, 3\}$.
* **Intersection ($\cap$)**
    * *Simple Meaning:* The set of elements found in **BOTH** set A **AND** set B. (Logical AND).
    * *Example:* $A=\{1, 2\}, B=\{2, 3\}$. $A \cap B = \{2\}$.
* **Complement ($A^c$)**
    * *Simple Meaning:* All elements **NOT** in set $A$ (from the total pool of possibilities).
    * *Example:* If the total pool is $\{1, 2, 3, 4, 5\}$ and $A=\{1, 2, 3\}$, then $A^c = \{4, 5\}$.

---

## Comparison Operators
*(The basic logic gates for decision-making.)*

* **Greater Than or Equal To ($\ge$)**
    * *Example:* $a \ge b$ (Is $a$ 5 or more if $b$ is 5?).
* **Less Than or Equal To ($\le$)**
    * *Example:* $a \le b$ (Is $a$ 5 or less if $b$ is 5?).
* **Equality ($==$)**
    * *Example:* $a == b$ (Are $a$ and $b$ exactly the same value?).
* **Inequality ($!=$)**
    * *Example:* $a != b$ (Are $a$ and $b$ different values?).

---

## Eigenvalues and Scalars
*(Used in data compression and finding important patterns.)*

* **Lambda (Eigenvalue) ($\lambda$)**
    * *Simple Meaning:* A **scalar** (just a single number) that describes how much an eigenvector is scaled by a matrix transformation. It represents the "strength" of the direction.
    * *Example:* In data compression (PCA), a large $\lambda$ means its corresponding direction (eigenvector) contains a lot of variance and is **important** to keep.
* **Eigenvector ($v$)**
    * *Simple Meaning:* A **special vector** (direction) that, when multiplied by a matrix, only changes its length, not its original direction.
    * *Example:* The eigenvectors found by PCA show the principal directions (the axes of maximum spread) in your data.

---

## Functions and Operators
*(Tools for calculation and optimization.)*

* **Maximum Function ($\max(...)$)**
    * *Simple Meaning:* Finds the **largest value** in a set.
    * *Example:* $\max(4, 7, 2) = 7$. Used in optimization to find the highest probability or best score.
* **Minimum Function ($\min(...)$)**
    * *Simple Meaning:* Finds the **smallest value** in a set.
    * *Example:* $\min(4, 7, 2) = 2$. Used in optimization to find the **minimum error** (what the AI is trying to achieve).
* **Reciprocal ($1 / ...$)**
    * *Simple Meaning:* Inverts the value.
    * *Example:* The reciprocal of $x=5$ is $1/5 = 0.2$.
* **Ellipsis ($\dots$)**
    * *Simple Meaning:* Indicates that a sequence continues in the same pattern.
    * *Example:* $a_1 + a_2 + \dots + a_n$ means "keep adding until you reach the $n$-th term."

---

## Functions and Probability
*(The language of prediction and statistics.)*

* **Function Notation ($f(x)$)**
    * *Simple Meaning:* A rule where an **input ($x$) gives a unique output**.
    * *Example:* If $f(x) = x+1$, then $f(5) = 6$. Used to define the mathematical formula for an AI model.
* **Conditional Probability Distribution ($P(x | y)$)**
    * *Simple Meaning:* The probability of **$x$ happening, GIVEN that $y$ has already happened**.
    * *Example:* $P(\text{Umbrella} | \text{Rain})$: The probability I use an umbrella, knowing it is raining.
* **Expectation Operator ($E[...]$)**
    * *Simple Meaning:* The **average value** or the long-run expected result.
    * *Example:* If you bet \$10 with a 50% chance of winning \$20, the expectation $E$ is 0 (you break even).
* **Variance ($\text{Var}(X)$)**
    * *Simple Meaning:* Measures the **spread** or **scatter** of data points around the average. High variance means the data is very spread out.
    * *Example:* If the average grade is 70, a high variance means some students scored 10 and others 100.
* **Standard Deviation ($\sigma(X)$)**
    * *Simple Meaning:* The square root of the variance. It's the most common way to describe spread because it uses the original units.
    * *Example:* If $\sigma(X) = 5$, it means most of your data points are within 5 units of the average.
* **Covariance ($\text{Cov}(X, Y)$)**
    * *Simple Meaning:* Measures how much **two variables change together**.
    * *Example:* If X is height and Y is weight, they have a positive covariance (as height increases, weight tends to increase).
* **Correlation ($\rho(X, Y)$)**
    * *Simple Meaning:* A standardized version of covariance, scaled to be between **-1 and 1**. It shows the **strength and direction** of the linear relationship.
    * *Example:* A correlation of $0.95$ means the two variables are very strongly related and move in the same direction.
