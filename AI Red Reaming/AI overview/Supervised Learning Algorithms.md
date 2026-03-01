# 🧠 Supervised Learning: The "Teacher" Method

## The Core Concept:
**Supervised Learning** is like teaching a child with flashcards. You show the computer data (the flashcard) and tell it the **correct answer (the label)**. By seeing enough examples, the computer learns to recognize the patterns on its own.

**Goal:**
To create a "**Mapping Function**" (a rule) that connects **Inputs ($X$)** to **Outputs ($Y$)** so accurately that when you show it new data without an answer, it gets it right. 

<img width="2048" height="1602" alt="image" src="https://github.com/user-attachments/assets/32d22e94-0e39-4822-a2dc-93ef97d4546a" />


---

## 1. The Two Main Types
Everything in supervised learning usually falls into one of these two buckets:

| Type | Classification | Regression |
| :--- | :--- | :--- |
| **Goal** | Sort things into **Categories**. | Predict a **Continuous Number**. |
| **Question** | "Is this A or B?" | "How much?" or "How many?" |
| **Examples** | • Spam vs. Not Spam<br>• Cat vs. Dog<br>• Fraud vs. Safe | • House Prices<br>• Stock Market Value<br>• Temperature Forecast |

---

## 2. Key Vocabulary (The "Lingo")
To sound professional, you need to know these components:

* **Training Data**: The textbook. The labeled dataset used to teach the model.
* **Features**: The "**Clues**" or Input variables.
    * *Example*: If predicting a house price, features are Size, Location, Bedrooms.
* **Labels**: The "**Answer Key**" or Output variable.
    * *Example*: The actual price of the house ($\$400,000$).
* **Model**: The "**Student**." The mathematical engine that learns the relationship between Features and Labels.
* **Training**: The "**Studying**." The process of adjusting the model until it stops making mistakes on the training data.

---

## 3. Using the Model: Prediction vs. Inference

* **Prediction**: Focuses on the **result**.
    * *Use*: "Just tell me if this email is spam."
* **Inference**: Focuses on **understanding**.
    * *Use*: "Tell me *why* you think this is spam? Which words mattered most?" (Understanding relationships and underlying structure).

---

## 4. The "Goldilocks" Problem: Fit
Getting the model to learn just right is the hardest part. 

<img width="3999" height="1740" alt="image" src="https://github.com/user-attachments/assets/d1e07b27-2635-489a-9a7e-7af3ad47dceb" />



* **Underfitting (Too Simple)**:
    * The model didn't study enough. It misses the patterns.
    * *Result*: Bad performance on training data AND new data.
* **Overfitting (Too Complex)**:
    * The model "memorized" the specific answers instead of learning the rules. It even memorized the noise/errors.
    * *Result*: Great score on training data, but fails on new, unseen data.
* **Generalization (The Goal)**:
    * The model learned the general concepts well enough to apply them to **brand-new data (unseen scenarios)**.

---

## 5. How We Fix & Measure It

### Evaluation Metrics (Grading the Model)

* **Accuracy**: How often is it right? (Total Correct / Total Predictions).
* **Precision**: When it claims something is "Positive," how often is it actually positive? (**Quality**).
* **Recall**: Out of all the actual "Positives" in the world, how many did it find? (**Quantity**).
* **F1-Score**: The balance between Precision and Recall. Use this if you have uneven data.

### Techniques to Improve Performance

* **Cross-Validation**:
    * *Concept*: Don't just rely on one test. Split your data into several "**folds**" (parts). Train on some, test on others, then rotate.
    * *Benefit*: Gives you a much more reliable estimate of how the model will perform in the real world.
* **Regularization**:
    * *Concept*: Punishing the model if it gets too complex. It forces the model to choose simpler explanations, which usually prevents Overfitting.
    * **L1 Regularization**: Can shrink less important features to zero (removes them).
    * **L2 Regularization**: Shrinks features to be very small but keeps them (reduces their impact).


# 📈 Linear Regression: Quick Reference Notes

## 1. Core Concept
**Linear Regression** is a supervised learning algorithm used to predict a **continuous target variable** (a number) based on independent variables.

* **The Goal:** Find the "Line of Best Fit" (a straight line) that passes as close as possible to all data points.
* **The Analogy:** Predicting a house's price based on size.
    * *Observation:* As size increases, price usually increases.
    * *Model:* The line quantifies exactly how much price increases for every extra square foot.

---

## 2. Regression vs. Classification
Before using the model, ensure you are solving a **Regression** problem, not a Classification one.

| Feature | **Regression** | **Classification** |
| :--- | :--- | :--- |
| **Goal** | Predict a specific **quantity**. | Predict a **category** or label. |
| **Output** | Continuous number (e.g., 100.5, 5000). | Discrete Class (e.g., "Spam", "Yes"). |
| **Examples** | House Price, Temperature, Sales. | Email Spam Filters, Image Recognition. |

---

## 3. The Mathematics

### A. Simple Linear Regression (One Predictor)
Used when predicting a target based on a **single** input variable.

> **Equation:** `y = mx + c`

* **y**: The predicted value (Target).
* **x**: The input variable (Predictor).
* **m**: The slope (How much `y` changes when `x` changes).
* **c**: The intercept (The value of `y` when `x` is 0).

### B. Multiple Linear Regression (Multiple Predictors)
Used when predicting a target based on **two or more** input variables (e.g., Size + Location + Age).

> **Equation:** `y = b0 + b1x1 + b2x2 + ... + bnxn`

* **b0**: The y-intercept.
* **x1, x2...**: The different input variables.
* **b1, b2...**: The coefficients (weights) for each specific variable.

---

## 4. How the Model Learns: Ordinary Least Squares (OLS)
How does the computer find the "Best Fit"? It uses **OLS**.

**The Objective:** Minimize the error between the *predicted* value and the *actual* value.

**The Steps:**
1.  **Calculate Residuals:** Find the difference between the real data point and the regression line.
2.  **Square the Residuals:** Square the values to make them all positive and penalize large errors heavily.
3.  **Sum the Squares (RSS):** Add them all up to get the *Residual Sum of Squares*.
4.  **Minimize:** The algorithm adjusts the line (the slopes and intercepts) until this sum is the smallest number possible.

---

## 5. Key Assumptions
For Linear Regression to be accurate, your data must meet 4 criteria:

1.  **Linearity:** There is actually a linear (straight-line) relationship between inputs and output.
2.  **Independence:** Data points are not affecting one another (e.g., one customer's purchase doesn't force another's).
3.  **Homoscedasticity:** Constant variance of errors.
    * *Simple English:* The "tube" of errors around the line should be roughly the same width all the way along the line. It shouldn't fan out like a cone.
4.  **Normality:** The errors (residuals) follow a Normal Distribution (Bell Curve).




# 📉 Logistic Regression: Quick Reference Notes

## 1. Core Concept
**Logistic Regression** is a supervised learning algorithm used for **Classification**, not Regression (despite its name).

* **The Goal:** Predict the probability that a data point belongs to a specific category.
* **The Output:** A probability score between **0 and 1**.
* **The Use Case:** Binary Classification (Yes/No, True/False, 0/1).
    * *Example:* Is this email Spam? (Output: 0.95 probability = Yes).

---

## 2. Classification vs. Regression
Make sure you are using the right tool.

| Feature | **Regression** (Linear) | **Classification** (Logistic) |
| :--- | :--- | :--- |
| **Output** | A continuous number (e.g., Price = $500k). | A discrete class/label (e.g., Is Spam? = Yes). |
| **Question** | "How much?" or "How many?" | "Which one?" or "Is it A or B?" |

---

## 3. The Math: The Sigmoid Function
Linear regression produces a straight line that can go to infinity. Logistic Regression needs to "squash" that line so the answer stays between 0 and 1 (0% to 100%).

It uses the **Sigmoid Function** (S-Curve):

$$P(x) = \frac{1}{1 + e^{-z}}$$

<img width="485" height="323" alt="image" src="https://github.com/user-attachments/assets/7caf4a54-255d-459c-935c-fdede2e78357" />


* **$P(x)$**: The predicted probability.
* **$e$**: Euler's number (approx 2.718).
* **$z$**: The linear input ($mx + c$).

**How it works visually:**



* If the input is very negative, the output is close to **0**.
* If the input is very positive, the output is close to **1**.
* It curves smoothly in an "S" shape.

---

## 4. Making the Decision: Thresholds & Boundaries

### The Threshold
The model gives you a probability (e.g., 0.8), but you need a hard label (Yes or No). We use a **Threshold**.
* **Standard Threshold:** 0.5
* **Logic:**
    * If Prediction > 0.5 $\rightarrow$ Class 1 (Positive/Yes)
    * If Prediction < 0.5 $\rightarrow$ Class 0 (Negative/No)

### The Decision Boundary & Hyperplanes
The "line" that splits your data classes apart is called the **Decision Boundary**.


<img width="699" height="537" alt="image" src="https://github.com/user-attachments/assets/253ed304-cf04-42f8-a718-329ae9d2b0e9" />



* **In 2D (2 features):** The boundary is a **Line**.
* **In 3D (3 features):** The boundary is a flat **Plane**.
* **In 4D+ (Many features):** The boundary is called a **Hyperplane**.
    * *Simple definition:* A flat subspace that slices the data into two halves.

---

## 5. Key Assumptions
For Logistic Regression to work best, check these requirements:

1.  **Binary Outcome:** The target must be categorical with two options (0 or 1).
2.  **Linearity of Log Odds:** The relationship between features and the *log-odds* of the outcome is linear.
3.  **No Multicollinearity:** The input variables (predictors) should not be highly correlated with each other (e.g., don't use "Age in Years" and "Age in Months" as two separate inputs).
4.  **Large Sample Size:** Generally requires more data than simple linear regression to be reliable.



# 🌳 Decision Trees: Quick Reference Notes

## 1. Core Concept
**Decision Trees** are a supervised learning algorithm used for both **Classification** (Categories) and **Regression** (Numbers).

* **The Logic:** It works like a flowchart or a game of "20 Questions." It breaks data down by asking a series of Yes/No (or True/False) questions to reach a conclusion.
* **The Goal:** Create a model that predicts a target value by learning simple decision rules from data features.



---

## 2. Anatomy of the Tree
A tree consists of three specific types of "nodes":

1.  **Root Node:** The starting point. It contains the entire dataset before any splitting happens.
2.  **Internal Nodes:** The "Decision Points." These represent a specific feature (e.g., "Is it raining?"). They branch out into two or more directions.
3.  **Leaf Nodes:** The "Answer." These are the endpoints that hold the final prediction (e.g., "Play Tennis" or "Don't Play").

---

## 3. How the Model Builds (The Math)
The tree needs to decide **which question to ask first** (and second, and third...). It chooses the question that best separates the data into "pure" groups.

It uses one of these three metrics to make that choice:

### A. Gini Impurity
Measures the probability of being wrong if you picked a random label.
* **Goal:** Lower is better (0 = Perfectly Pure).
* **Formula:**
    $$Gini(S) = 1 - \sum (p_i)^2$$
    *(Where $p_i$ is the probability of a specific class).*

### B. Entropy
Measures the "disorder" or chaos in the set.
* **Goal:** Lower is better (Low Entropy = High Order).
* **Formula:**
    $$Entropy(S) = - \sum p_i \cdot \log_2(p_i)$$



### C. Information Gain
Measures how much "Information" we gained by splitting the data on a specific feature.
* **Goal:** Higher is better.
* **Logic:** It compares the Entropy *before* the split to the weighted Entropy *after* the split. The difference is the "Gain."
    $$Gain = Entropy(Parent) - Weighted Average Entropy(Children)$$

---

## 4. The "Play Tennis" Example
Imagine predicting if we should play tennis based on weather.

**The Dataset:**
* **Features:** Outlook (Sunny/Overcast/Rainy), Temp, Humidity, Wind.
* **Target:** Play Tennis (Yes/No).

**The Process:**
1.  **Root:** The algorithm checks all features. It finds that **Outlook** gives the highest Information Gain.
2.  **Split 1:** It splits the data into three branches: Sunny, Overcast, Rainy.
3.  **Recursive Step:**
    * If **Overcast** $\rightarrow$ It sees all examples are "Yes." It creates a Leaf Node (Yes).
    * If **Sunny** $\rightarrow$ It's mixed. It looks for the next best feature (e.g., Humidity) and splits again.
    * If **Rainy** $\rightarrow$ It's mixed. It looks for the next best feature (e.g., Wind) and splits again.



---

## 5. Stopping the Tree
If we don't stop it, the tree will grow until every single data point has its own leaf (Overfitting). We use **Stopping Criteria**:

* **Max Depth:** Limit how many "layers" the tree can have.
* **Min Samples:** Don't split a node if it has too few data points (e.g., less than 5).
* **Pure Nodes:** Stop if a node contains only one class (100% accuracy for that group).

---

## 6. Key Advantages (Assumptions)
Decision trees are very flexible compared to Linear/Logistic Regression.

1.  **No Linearity Assumption:** Can handle complex, non-linear relationships.
2.  **No Normality Assumption:** Data does not need to be a Bell Curve.
3.  **Handles Outliers:** Outliers generally don't break the model because the tree splits based on thresholds/values, not average distances.
4.  **Interpretability:** You can literally visualize the logic (White Box model).


# Naive Bayes: The Simple Explanation

**Naive Bayes** is a classification algorithm. Think of it as a "probability calculator." It looks at the features of an object (like words in an email) and calculates the probability that the object belongs to a specific category (like "Spam" or "Not Spam").

It is famous for being:
* **Simple:** Easy to build.
* **Fast:** Great for huge datasets.
* **Effective:** Surprisingly good at things like Spam Filtering and Sentiment Analysis.

---

## Part 1: The Foundation (Bayes' Theorem)

Before we get to the "Naive" part, we must understand the engine: **Bayes' Theorem**.

### The Core Concept
Bayes' Theorem is a way to **update your beliefs** when you get new evidence.
* **Old Belief:** "I probably don't have this rare disease."
* **New Evidence:** "I tested positive."
* **Updated Belief:** "I might have the disease, but I need to calculate exactly how likely that is."

### The Formula (Simplified)
Don't let the math scare you. It’s just ratios.

$$P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}$$

| Symbol | Name | Plain English Meaning |
| :--- | :--- | :--- |
| **P(A\|B)** | **Posterior** | The probability of **A** (Event) being true *after* seeing **B** (Evidence). |
| **P(B\|A)** | **Likelihood** | If **A** is true, how likely is it that we would see **B**? |
| **P(A)** | **Prior** | How likely was **A** in the first place (before seeing evidence)? |
| **P(B)** | **Evidence** | How likely is **B** to happen generally (regardless of A)? |

---

### Real-World Example: The Medical Test

Imagine a disease and a test result.
* **Event A:** You have the disease.
* **Event B:** You test positive.

**The Data:**
1.  **P(A) (Prior):** Only **1%** (0.01) of people have the disease.
2.  **P(B|A) (Likelihood):** If you are sick, the test is correct **95%** (0.95) of the time.
3.  **False Positives:** If you are healthy, the test is wrong **5%** (0.05) of the time.

**The Calculation:**
You test positive. Are you definitely sick? Let's use the theorem.

**Step 1: Calculate P(B) [Total probability of a positive test]**
We need to add up *all* the ways to get a positive result:
1.  Sick people testing positive: $0.01 \times 0.95 = 0.0095$
2.  Healthy people testing positive (False alarms): $0.99 \times 0.05 = 0.0495$
3.  **Total P(B):** $0.0095 + 0.0495 = \mathbf{0.059}$

**Step 2: Apply the Formula**
$$P(\text{Sick}|\text{Positive}) = \frac{0.95 \times 0.01}{0.059} \approx \mathbf{16.1\%}$$

**The Takeaway:**
Even with a 95% accurate test, you only have a **16.1%** chance of actually being sick. This is because the disease is so rare that the "False Alarms" outnumber the "Real Cases." Bayes' theorem helps us see this reality.

---

## Part 2: Why is it called "Naive"?

This algorithm applies Bayes' Theorem to data with many features. However, it makes a **"Naive" Assumption**:

> **The Assumption of Independence:**
> It assumes that all features are unrelated to each other.

**Example:**
If you are analyzing an email to see if it is "Spam":
* The algorithm sees the word "Free".
* It sees the word "Money".
* It calculates the probability of "Free" indicating spam.
* It calculates the probability of "Money" indicating spam.

**The "Naive" part:** It treats "Free" and "Money" as if they have nothing to do with each other. In reality, they often go together (dependent), but Naive Bayes pretends they don't to make the math simpler and faster.

---

## Part 3: How Naive Bayes Works (The Steps)

If we want to classify a new data point (e.g., a new email):

1.  **Calculate Priors:**
    What is the general probability of *any* email being Spam vs. Not Spam? (e.g., 20% are Spam, 80% are Not).

2.  **Calculate Likelihoods:**
    If an email *is* Spam, what is the probability it contains the word "Viagra"?
    If an email *is* Not Spam, what is the probability it contains the word "Meeting"?

3.  **Apply Bayes' Theorem:**
    Combine the Priors and Likelihoods for all the words in the new email to get a score for both "Spam" and "Not Spam."

4.  **Predict:**
    Compare the scores. Whichever class has the higher probability wins.

---

## Part 4: The Three Types of Naive Bayes

Different data types require different versions of the algorithm.

| Type | Best Used For... | Example |
| :--- | :--- | :--- |
| **Gaussian** | **Continuous Numbers** (Bell Curve) | Predicting if a user buys a product based on **Age** or **Salary**. |
| **Multinomial** | **Counts** (How often something appears) | Spam filtering based on **word counts** (e.g., "Free" appears 3 times). |
| **Bernoulli** | **Binary** (Yes/No) | Text classification checking only if a word **exists or not** (doesn't care how many times). |

---

## Part 5: Summary of Pros, Cons & Assumptions

**The Main Assumption:**
* **Feature Independence:** As mentioned, it assumes Feature A has no effect on Feature B. Even though this is often wrong in real life, the algorithm still works surprisingly well.

**Data Requirements:**
* **Sufficient Data:** You need enough historical data to calculate the probabilities accurately.
* **Distribution:** You must pick the right type (Gaussian vs. Multinomial) to match your data's shape.


## Example: Spam Filtering with Naive Bayes

To understand how this works in real life, let's pretend we are building a spam filter. We will use a technique called **"Bag of Words."**

Imagine we have two literal bags:
1.  **The Spam Bag**
2.  **The Ham (Not Spam) Bag**

## Step 1: The Training Data (Teaching the Robot)
We feed the algorithm 3 previous emails that we have already labeled.

| Email ID | Content | Label |
| :--- | :--- | :--- |
| 1 | "Win **money** now" | **SPAM** |
| 2 | "Work **meeting** tonight" | **HAM** |
| 3 | "Win free **money**" | **SPAM** |

**Current Stats:**
* **Total Emails:** 3
* **Probability of Spam (Prior):** 2/3
* **Probability of Ham (Prior):** 1/3

## Step 2: Filling the "Bags" (Likelihoods)
We dump all the words from the Spam emails into the Spam Bag, and Ham emails into the Ham Bag.

**The Spam Bag contains (6 words total):**
* "Win" (2)
* "Money" (2)
* "Now" (1)
* "Free" (1)

**The Ham Bag contains (3 words total):**
* "Work" (1)
* "Meeting" (1)
* "Tonight" (1)

## Step 3: The New Email (The Test)
A new email arrives. We need to classify it.
> **New Email:** "Win Money"

We assume the words are independent (The "Naive" part). We check the probability of finding these specific words in each bag.

### Calculation A: Is it Spam?
We multiply the **Prior** (Chance of being Spam generally) by the **Likelihood** of the words appearing in the Spam bag.

* **Prior:** $P(Spam) = \frac{2}{3}$
* **Word "Win":** Appears 2 times in the Spam bag (out of 6 total words). $P = \frac{2}{6}$
* **Word "Money":** Appears 2 times in the Spam bag (out of 6 total words). $P = \frac{2}{6}$

**Spam Score:**
$$\frac{2}{3} \times \frac{2}{6} \times \frac{2}{6} = \mathbf{0.074}$$

### Calculation B: Is it Ham?
We do the same for the Ham bag.

* **Prior:** $P(Ham) = \frac{1}{3}$
* **Word "Win":** Appears 0 times in Ham bag. *(Usually, we add a tiny number like +1 so this doesn't become zero, but for this simple example, let's say it's extremely low).*
* **Word "Money":** Appears 0 times in Ham bag.

**Ham Score:**
$$\frac{1}{3} \times 0 \times 0 = \mathbf{0.0}$$

## Step 4: The Verdict
* **Spam Score:** 0.074
* **Ham Score:** 0.0
* **Result:** The email is classified as **SPAM**.

---

### Why "Naive" works here
Notice that the algorithm didn't care about the *order* of the words. "Money Win" would have gotten the exact same score as "Win Money." Even though it ignored the sentence structure, it correctly identified that "Win" and "Money" are words that heavily "vote" for the Spam category.


# Support Vector Machines (SVM): The Complete Guide

**Support Vector Machines (SVMs)** are powerful supervised learning algorithms used for **Classification** (grouping things) and **Regression** (predicting numbers).

Think of SVM as a **Perfectionist Algorithm**. It doesn't just want to separate two groups of data; it wants to separate them with the **widest possible safety gap**.

---

## Part 1: The Core Concept (Linear SVM)

### 1. The Goal: Maximizing the Margin
Imagine you have red dots and blue dots on a piece of paper. You want to draw a straight line to separate them.
* **Bad Line:** A line that passes very close to the dots. It's risky.
* **SVM Line:** A line that is exactly in the middle of the widest gap between the two groups.

This "gap" is called the **Margin**. SVM tries to find the **Optimal Hyperplane** that maximizes this margin.



### 2. Key Terminology

| Term | Definition | The Analogy |
| :--- | :--- | :--- |
| **Hyperplane** | The decision boundary. In 2D, it's a line. In 3D, it's a flat plane. | The center line of a road. |
| **Margin** | The distance between the hyperplane and the nearest data points. | The width of the road (we want it wide!). |
| **Support Vectors** | The specific data points that lie on the very edge of the margin. | The "pillars" holding up the road. |

> **Note:** The "Support Vectors" are the *only* data points that matter. If you deleted all the other points far away from the line, the line wouldn't move. These specific points "support" the decision boundary.

### 3. The Math (Simplified)
The hyperplane is defined by this equation:

$$w \cdot x + b = 0$$

* **$x$:** The input features (the data).
* **$w$ (Weight):** Controls the **orientation/angle** of the hyperplane.
* **$b$ (Bias):** Controls the **position** (shifts the line up/down or left/right).

During training, the SVM adjusts $w$ and $b$ to find the widest street.

---

<img width="317" height="159" alt="image" src="https://github.com/user-attachments/assets/1f6d9cdf-668f-4e7b-a550-6c7b1add7a27" />

## Part 2: Non-Linear SVM (The "Kernel Trick")

In the real world, data is rarely clean. Sometimes, the Red dots are clumped in the middle, surrounded by a ring of Blue dots. You cannot draw a straight line to separate them. This is **Non-Linearly Separable** data.

To solve this, SVM uses the **Kernel Trick**.

### 1. The Analogy: "Lifting the Marbles"
Imagine Red and Blue marbles sitting on a flat table (2D). The Red ones are in the center. You can't separate them with a straight stick.

Now, imagine you slap the bottom of the table in the center:
1.  The Red marbles fly up into the air (3D space).
2.  The Blue marbles stay low.
3.  Now that they are in 3D, you **can** slide a flat sheet (a plane) between the flying Red marbles and the sitting Blue marbles.



### 2. What is a Kernel Function?
A Kernel Function is the math that "lifts" the data from low dimensions (2D) to high dimensions (3D or more) where it becomes easy to separate.

**Common Kernel Types:**
* **Polynomial Kernel:** Adds curved lines (like $x^2$ or $x^3$). Good for slightly curved data.
* **Radial Basis Function (RBF):** The most popular choice. It uses a Gaussian function to create complex "bubbles" or regions around data. It handles very complex patterns.
* **Sigmoid Kernel:** Similar to Logistic Regression. Creates an S-shaped decision boundary.

### 3. Use Case: Image Classification
Non-Linear SVMs are great for images (e.g., Cats vs. Dogs).
* **Features:** Fur texture, ear shape, nose size.
* **Relationship:** These features interact in complex ways (non-linear).
* **Result:** The Kernel Trick allows SVM to separate "Cat" patterns from "Dog" patterns even though a straight line couldn't do it.

---

## Part 3: The Optimization Problem

How does the computer actually find the answer? It solves a math problem:

**Minimize:**
$$\frac{1}{2} ||w||^2$$

**Subject to:**
$$y_i(w \cdot x_i + b) \geq 1$$

**Translation:**
1.  **Minimize $||w||$:** In SVM math, making $w$ smaller actually makes the **Margin** bigger. So, this line means **"Maximize the Margin."**
2.  **Subject to...:** This constraint ensures we don't cheat. It says, "Maximize the margin, BUT ensure every data point is still classified correctly on the right side of the road (by a distance of at least 1)."

---

## Part 4: Summary of Assumptions

Why choose SVM?
1.  **High Dimensionality:** It works great even if you have more features (columns) than data points (rows).
2.  **Robust:** It ignores outliers because it only cares about the Support Vectors (the edge cases).
3.  **No Distribution Assumptions:** You don't need to worry if your data follows a Bell Curve or not.
