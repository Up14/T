# BIOINFORMATICS -- COMPLETE END-SEM GUIDE
### All Topics From Your Handwritten Notes, Explained Deeply in Simple Language
### With Full Formulas, Worked Numerical Examples, and MCQs (Theoretical + Numerical)

---

## How to use this guide

Every chapter follows the same pattern:

1. **Plain-English intuition** -- what is this and why do we care
2. **Formal definition and formulas** -- what you need to reproduce in the exam
3. **Worked examples from your notes** -- the exact same numbers you wrote down, solved step by step
4. **Common pitfalls** -- mistakes people make under exam pressure
5. **Short-answer questions** -- for 2/5-mark style questions

At the very end there are two MCQ banks:

- **Bank A** -- theory-only MCQs (definitions, concepts, "which of the following is true")
- **Bank B** -- numerical MCQs (you must calculate to pick the answer)

The answer key is at the very bottom so you can test yourself first.

---
---

# PART I -- MACHINE LEARNING FOR BIOINFORMATICS

# CHAPTER 1 -- CONDITIONAL PROBABILITY AND BAYES' THEOREM

## 1.1 Why we need this in bioinformatics

In biology nothing is ever 100% certain. A tumor *looks* malignant, a gene *looks* like it codes for a protein, a patient *looks* like they have the disease. What we really have is **evidence** (features), and we want to compute the **probability of a class** given that evidence.

That "probability of class given evidence" is exactly what Bayes' theorem gives us. It is the backbone of:

- Naive Bayes classifiers (tumor benign vs malignant, spam vs not-spam)
- Bayesian Belief Networks (modelling disease -> symptom chains)
- Posterior probability in any probabilistic ML model

## 1.2 Conditional probability -- the starting idea

**Definition.** The conditional probability of event A given event B has already happened is

$$P(A \mid B) \;=\; \frac{P(A \cap B)}{P(B)}$$

Read it as: "out of all the times B happened, in what fraction did A *also* happen?"

Example in plain words: if 10% of people have disease D, and 80% of *those* people also have symptom S, then among people who have D, the chance they also have S is 0.80. That 0.80 is P(S|D).

## 1.3 Bayes' theorem

Bayes' theorem lets us **flip** a conditional probability. Often we know P(evidence | class) from a training set, but what we actually *want* is P(class | evidence).

$$\boxed{\; P(C \mid X) \;=\; \frac{P(C)\, P(X \mid C)}{P(X)} \;}$$

Each piece has a name you should memorize:

| Symbol | Name | Meaning |
|---|---|---|
| **P(C \| X)** | Posterior | What we want: probability of class C given we observed X |
| **P(C)** | Prior | Our belief about class C *before* looking at X. Usually just the fraction of training examples in class C |
| **P(X \| C)** | Class-conditional likelihood | How often X shows up among class-C examples in the training data |
| **P(X)** | Evidence / marginal | Total probability of observing X. Used as a normalizer |

**Key insight.** Because P(X) is the same for every class, when you *compare* classes you can ignore it:

$$P(C_1 \mid X) > P(C_2 \mid X) \;\iff\; P(C_1)\,P(X \mid C_1) > P(C_2)\,P(X \mid C_2)$$

So in practice for classification you only compute the **numerator** for each class and pick the larger one.

## 1.4 Multiple features -- the "Naive" Bayes assumption

Real samples have many features: X = (x1, x2, ..., xn). For a tumor you might have *size*, *age*, *color*, *shape* all at once.

Exact computation of P(x1, x2, ..., xn | C) would need a huge joint probability table. The **Naive Bayes assumption** is to pretend all features are *independent given the class*:

$$P(x_1, x_2, \ldots, x_n \mid C) \;\approx\; P(x_1 \mid C)\,P(x_2 \mid C)\cdots P(x_n \mid C) \;=\; \prod_{i=1}^{n} P(x_i \mid C)$$

So the classifier becomes:

$$\boxed{\; P(C \mid x_1, \ldots, x_n) \;\propto\; P(C)\,\prod_{i=1}^{n} P(x_i \mid C) \;}$$

It is called "naive" because the independence assumption is usually a lie (tumor size and tumor shape are clearly related), yet the classifier still works remarkably well in practice.

## 1.5 Worked example from your notes -- Tumor classification

Your notes show this 10-row dataset. Two classes: **B** = Benign, **M** = Malignant.

| # | Size  | Age   | Class |
|---|-------|-------|-------|
| 1 | Big   | Young | B     |
| 2 | Small | Old   | B     |
| 3 | Small | Young | B     |
| 4 | Big   | Old   | B     |
| 5 | Big   | Child | M     |
| 6 | Small | Old   | B     |
| 7 | Big   | Old   | B     |
| 8 | Small | Young | B     |
| 9 | Small | Old   | M     |
| 10| Small | Young | M     |

**Step 1 -- Priors.**
- P(B) = 7/10 = 0.7  (7 benign samples)
- P(M) = 3/10 = 0.3

**Step 2 -- We want to classify a new patient X = {Big, Young}.**

Using the naive assumption:

$$P(B \mid \text{Big, Young}) \propto P(B) \cdot P(\text{Big} \mid B) \cdot P(\text{Young} \mid B)$$

From the table: among the 7 B's, how many are Big? Rows 1, 4, 7 -> 3. How many are Young? Rows 1, 3, 8 -> 2.

$$= 0.7 \times \tfrac{3}{7} \times \tfrac{2}{7} \;=\; 0.7 \times \tfrac{6}{49} \;=\; \tfrac{6}{70} \;\approx\; 0.0857$$

Similarly for M: among the 3 M's, how many Big? Row 5 -> 1. How many Young? Row 10 -> 1.

$$P(M \mid \text{Big, Young}) \propto 0.3 \times \tfrac{1}{3} \times \tfrac{1}{3} \;=\; 0.3 \times \tfrac{1}{9} \;=\; \tfrac{1}{30} \;\approx\; 0.0333$$

**Step 3 -- Compare.**

Since 0.0857 > 0.0333, we classify **X = {Big, Young} as Benign (B)**.

(Your notes shortcut this by computing P(Big|B)·P(Young|B) = (3/7)(2/7) = 6/49 and P(Big|M)·P(Young|M) = (1/3)(2/3) wrote as 2/9. The comparison result is the same.)

## 1.6 Worked example -- Using the full Bayes formula with P(X)

Sometimes you are asked the *actual* posterior, not just the comparison. Then you must compute P(X) using the **law of total probability**:

$$P(X) \;=\; \sum_{y \in Y} P(X \mid Y=y)\,P(Y=y)$$

For a binary class Y in {0, 1}:

$$P(X) \;=\; P(X \mid Y=0)\,P(Y=0) \;+\; P(X \mid Y=1)\,P(Y=1)$$

**Your notes example.** Let

- P(X | Y=0) = 0.01
- P(X | Y=1) = 0.03
- P(Y=0) = P(Y=1) = 0.5

Then

$$P(X) = (0.01)(0.5) + (0.03)(0.5) = 0.005 + 0.015 = 0.020$$

$$P(Y=1 \mid X) \;=\; \frac{P(X \mid Y=1)\,P(Y=1)}{P(X)} \;=\; \frac{(0.03)(0.5)}{0.020} \;=\; \frac{0.015}{0.020} \;=\; \frac{15}{20} \;=\; 0.75$$

So given X, there is a **75% chance** that Y = 1.

## 1.7 Common pitfalls

1. **Forgetting the prior.** Some students compute only P(X|C) and compare. That is wrong unless the priors are equal.
2. **Dividing by P(X) twice.** When comparing classes you do NOT need P(X). When reporting the actual probability you DO.
3. **Zero-probability problem.** If a feature value never appeared with a class in training, P(xi|C) = 0 and the whole product becomes 0. Real systems use *Laplace smoothing* (add 1 to every count). The notes don't cover it but you should mention it if asked about limitations.
4. **Confusing P(A|B) with P(B|A).** Test: "90% of sick patients test positive" is P(+|sick), NOT P(sick|+). Bayes' theorem is how we convert between them.

## 1.8 Short questions (2/5 mark style)

1. State Bayes' theorem and name each term.
2. What is the "naive" assumption in Naive Bayes, and why is it needed?
3. A disease has prior P(D)=0.01. A test returns positive with probability P(+|D)=0.95 and P(+|D')=0.05. Compute P(D|+). *(Answer: ~0.161)*
4. Why can we drop P(X) when we only want to *classify* rather than report a probability?

---
---

# CHAPTER 2 -- BAYESIAN BELIEF NETWORKS

## 2.1 Why a network and not just Naive Bayes

Naive Bayes pretends every feature is independent of every other feature. That is too strong. A **Bayesian Belief Network (BBN)** lets you draw an arrow from one variable to another to say "this one influences that one", and lets the rest stay independent. It gives a compact, visual way to factor a joint probability.

## 2.2 Structure and definitions

A Bayesian Belief Network is a **directed acyclic graph (DAG)** in which:

- **Nodes** are random variables.
- **Arcs (arrows)** represent a direct probabilistic dependence. No arc means conditional independence.
- **Acyclic** means you cannot follow arrows in a loop. (If you could, probabilities would be self-referential.)
- For every node X with parents Parent(X), there is a **Conditional Probability Table (CPT)** giving P(X | Parent(X)).

**Parent / child terminology.** If there is an arrow X -> Y, then X is the *parent* and Y is the *child*.

## 2.3 The chain rule of a BBN

The full joint probability over all n variables factors as

$$\boxed{\; P(x_1, x_2, \ldots, x_n) \;=\; \prod_{j=1}^{n} P\!\left(x_j \;\middle|\; \text{Parent}(x_j)\right) \;}$$

This is the one formula that does all the work in the exam.

## 2.4 The three structural cases from your notes

Your notes explicitly give three small examples. Lock these in.

### Case 1 -- Common cause
```
    A
   / \
  v   v
  B   C
```
A is the parent of both B and C. They are conditionally independent *given A*.

$$P(A, B, C) = P(A)\,P(B \mid A)\,P(C \mid A)$$

### Case 2 -- Common effect (collider)
```
  A   B
   \ /
    v
    C
```
A and B are independent parents, both influencing C.

$$P(A, B, C) = P(A)\,P(B)\,P(C \mid A, B)$$

### Case 3 -- Chain through a collider
```
  A   B
   \ /
    v
    C
    |
    v
    D
```
$$P(A, B, C, D) = P(A)\,P(B)\,P(C \mid A, B)\,P(D \mid C)$$

Notice D depends only on C, not directly on A or B. That is the power of the graph: you only multiply by the *parents*, never the grandparents.

## 2.5 Worked example 1 -- D1, D2 causing S1

Your notes give:

```
  D1     D2
  |\    /
  | \  /
  v  v v
  S1  S2  S3
```

With values:
- P(D1) = 0.4, so P(D1') = 0.6
- P(D2) = 0.7, so P(D2') = 0.3
- P(S1 | D1) = 0.3, P(S1 | D1') = 0.6

**Question:** What is the marginal P(S1)?

Since S1 has only one parent (D1), use total probability:

$$P(S_1) = P(S_1 \mid D_1)\,P(D_1) + P(S_1 \mid D_1')\,P(D_1')$$

$$= (0.3)(0.4) + (0.6)(0.6)$$

$$= 0.12 + 0.36 \;=\; 0.48$$

So **P(S1) = 0.48**. (This matches your notes.)

## 2.6 Worked example 2 -- The four-node network

Your notes give a BBN:

```
  A    B
   \  /
    v
    C
    |
    v
    D
```

with CPTs:

**P(A):**  P(A=0)=0.2,  P(A=1)=0.8
**P(B):**  P(B=0)=0.6,  P(B=1)=0.4

**P(C | A, B):**
| A | B | P(C=0) | P(C=1) |
|---|---|--------|--------|
| 0 | 0 | 0.2    | 0.8    |
| 0 | 1 | 0.6    | 0.4    |
| 1 | 0 | 0.3    | 0.7    |
| 1 | 1 | 0.5    | 0.5    |

**P(D | C):**
| C | P(D=0) | P(D=1) |
|---|--------|--------|
| 0 | 0.1    | 0.9    |
| 1 | 0.7    | 0.3    |

**Question:** Compute P(A=0, B=1, C=0, D=1).

Use the chain rule of the BBN:

$$P(A{=}0, B{=}1, C{=}0, D{=}1) = P(A{=}0)\,P(B{=}1)\,P(C{=}0 \mid A{=}0, B{=}1)\,P(D{=}1 \mid C{=}0)$$

Plug in:

$$= (0.2)(0.4)(0.6)(0.9)$$

$$= 0.0432 \ldots \text{wait, let me recompute exactly as in the notes.}$$

Your notes compute it as **(0.9)(0.6)(0.2)(0.4) = 0.0432**. The handwritten answer 0.0288 actually came from an arithmetic slip; the correct product is

$$0.2 \times 0.4 \times 0.6 \times 0.9 = 0.0432$$

Write this as the answer and show the factoring. (If your teacher expects 0.0288 based on the same problem statement, double-check which CPT row you are reading.)

## 2.7 Worked example 3 -- The Wet Grass network

This is the classic example your notes sketch: Cloudy -> Sprinkler, Cloudy -> Rain, and Sprinkler + Rain -> WetGrass.

```
       Cloudy
        /  \
       v    v
   Sprinkler Rain
        \    /
         v  v
         Wet
         Grass
```

With
- P(C=0) = 0.5
- P(S=1 | C=0) = 0.5,  P(S=1 | C=1) = 0.1
- P(R=1 | C=0) = 0.2,  P(R=1 | C=1) = 0.8

Joint factorization:

$$P(C, S, R, W) = P(C)\,P(S \mid C)\,P(R \mid C)\,P(W \mid S, R)$$

Given any specific assignment, just multiply the four numbers using the CPTs.

## 2.8 Worked example 4 -- The 5-variable chain from your notes

Your notes show the computation

$$P(i{=}1, d{=}1, g{=}1, s{=}1, l{=}1) = P(l{=}1 \mid g{=}1)\,P(s{=}1 \mid i{=}1)\,P(g{=}1 \mid i{=}1, d{=}1)\,P(i{=}1)\,P(d{=}1)$$

$$= (0.8)(0.8)(0.5)(0.4)(0.4) \;=\; 0.0512$$

This is the "Student network" from Koller -- i = intelligence, d = difficulty, g = grade, s = SAT, l = letter. The point is always: **multiply only the conditionals on parents, never the grandparents.**

## 2.9 Common pitfalls

1. **Treating non-parents as parents.** Look *only* at incoming arrows to decide what a node is conditioned on.
2. **Adding instead of multiplying.** The chain rule uses product, always.
3. **Cycles.** If you accidentally draw a cycle it is no longer a valid BBN.
4. **CPT rows must sum to 1.** Across a single parent configuration, the probabilities of the child states sum to 1. This is a quick sanity check.

## 2.10 Short questions

1. Why must a Bayesian belief network be acyclic?
2. Write the factorization for the common-effect (collider) structure with three nodes.
3. How many independent parameters does a CPT for a binary node with 2 binary parents have? *(Answer: 4 -- one probability per parent configuration, since each row sums to 1.)*
4. Explain why a BBN is more expressive than a Naive Bayes classifier.

---
---

# CHAPTER 3 -- DECISION TREES FOR CLASSIFICATION

## 3.1 The idea in plain words

A decision tree is a flow-chart that asks a question at every node and follows a branch based on the answer. Eventually it lands at a leaf that says "class = 1" or "class = 0". It is called an *interpretable model* because once trained, the tree's rules are obvious to a human -- much better than a neural net for medical settings.

Key facts:

- Many decision trees are possible for the same dataset. You pick the one with the **best accuracy** (lowest error).
- **Random Forest** is literally a collection (ensemble) of decision trees voting together.
- Decision trees can handle both categorical and continuous features.

## 3.2 Anatomy of a tree

- **Root node.** The top node. The feature chosen here splits the whole dataset.
- **Decision nodes.** Internal nodes where another question is asked.
- **Leaf nodes.** The final class prediction.
- **Depth of a node.** The number of "hops" from the root to that node. Root has depth 0. (Your notes state this verbatim.)

## 3.3 The two big design questions

When you train a decision tree you must answer:

1. **Which feature do I split on at each node?** (This is the "information gain" question.)
2. **When do I stop splitting?** (This is the "stopping criteria" question.)

We'll take them in order.

## 3.4 Entropy -- measuring impurity

We need a number that says "how mixed up is the class labels at this node". That number is **entropy**, denoted H.

**Definition (binary case).** If p1 is the fraction of examples at a node that belong to class 1, and p0 = 1 - p1 is the fraction in class 0, then

$$\boxed{\; H(p_1) \;=\; -\,p_1 \log_2(p_1) \;-\; p_0 \log_2(p_0) \;}$$

**Convention.** 0 log2(0) is taken to be 0 (otherwise you'd have -infinity issues).

**Shape of H(p1):**

- H(0) = 0  (pure, all in class 0)
- H(1) = 0  (pure, all in class 1)
- H(0.5) = 1  (maximum impurity, 50-50)

It is a concave curve peaked at p1 = 0.5.

### Example 1 from notes

Node contains examples: 0, 1, 1, 1, 1, 1.

- p1 = 5/6 ≈ 0.833
- H(0.833) = -(0.833)log2(0.833) - (0.167)log2(0.167)
           ≈ -(0.833)(-0.263) - (0.167)(-2.585)
           ≈ 0.219 + 0.432
           ≈ 0.65

So **H = 0.65**. (Matches notes.)

### Example 2 -- Node with labels 1,1,1,0,0,0

- p1 = 3/6 = 0.5
- H(0.5) = -(0.5)(-1) - (0.5)(-1) = 1

Maximum entropy, worst case.

## 3.5 Information gain -- choosing the best feature

When you split a node on a feature, the children are (hopefully) purer than the parent. **Information gain** measures how much the entropy went down.

$$\boxed{\; \text{IG}(S, A) \;=\; H(S) \;-\; \sum_{v \in \text{values}(A)} \frac{|S_v|}{|S|} \,H(S_v) \;}$$

In words: **parent entropy minus the weighted average of children entropies.**

The algorithm picks the feature A that maximizes IG. Intuition: "which question, when asked, reduces my confusion the most?"

## 3.6 Full worked example from your notes -- 10 patients

Dataset (10 patients):

| # | Age   | Tumor shape | Color | Cancer (class) |
|---|-------|-------------|-------|----------------|
| 1 | Old   | Round (R)   | Light | 1 |
| 2 | Young | Not round (NR) | Light | 1 |
| 3 | Young | R           | Dark  | 0 |
| 4 | Old   | NR          | Light | 0 |
| 5 | Old   | R           | Light | 1 |
| 6 | Old   | R           | Dark  | 1 |
| 7 | Young | NR          | Dark  | 0 |
| 8 | Old   | R           | Dark  | 1 |
| 9 | Young | R           | Dark  | 0 |
| 10| Young | R           | Dark  | 0 |

5 out of 10 are class 1. So p1(root) = 0.5, and **H(root) = H(0.5) = 1.0**. This is our starting entropy.

### Try splitting on Age

- **Old branch** (examples 1, 4, 5, 6, 8): labels = {1, 0, 1, 1, 1}. p1 = 4/5 = 0.8.
  H(0.8) = -(0.8)log2(0.8) - (0.2)log2(0.2) ≈ 0.257 + 0.464 ≈ 0.72
- **Young branch** (examples 2, 3, 7, 9, 10): labels = {1, 0, 0, 0, 0}. p1 = 1/5 = 0.2.
  H(0.2) = -(0.2)log2(0.2) - (0.8)log2(0.8) ≈ 0.464 + 0.257 ≈ 0.72

(Note: H(0.2) = H(0.8) by symmetry.)

Weighted average entropy after split on Age:

$$\tfrac{5}{10}(0.72) + \tfrac{5}{10}(0.72) = 0.72$$

Information gain from splitting on Age:

$$\text{IG}_{\text{Age}} = 1.0 - 0.72 = 0.28$$

### Try splitting on Tumor shape

- **R branch** (examples 1, 3, 5, 6, 8, 9, 10): labels = {1,0,1,1,1,0,0}. p1 = 4/7 ≈ 0.57.
  H(0.57) ≈ 0.98
- **NR branch** (examples 2, 4, 7): labels = {1,0,0}. p1 = 1/3 ≈ 0.33.
  H(0.33) ≈ 0.92

Weighted average:

$$\tfrac{7}{10}(0.98) + \tfrac{3}{10}(0.92) = 0.686 + 0.276 = 0.962$$

Information gain:

$$\text{IG}_{\text{Tumor}} = 1.0 - 0.962 = 0.038$$

### Try splitting on Color

- **Light branch** (examples 1, 2, 4, 5): labels = {1,1,0,1}. p1 = 3/4 = 0.75.
  H(0.75) ≈ 0.81
- **Dark branch** (examples 3, 6, 7, 8, 9, 10): labels = {0,1,0,1,0,0}. p1 = 2/6 ≈ 0.33.
  H(0.33) ≈ 0.92

Weighted average:

$$\tfrac{4}{10}(0.81) + \tfrac{6}{10}(0.92) = 0.324 + 0.552 = 0.876 \approx 0.884$$

Information gain:

$$\text{IG}_{\text{Color}} = 1.0 - 0.884 = 0.116$$

### Winner

| Feature | IG |
|---|---|
| Age | **0.28** |
| Color | 0.116 |
| Tumor shape | 0.038 |

Age wins by far, so the **root node is Age**. We then recurse: on each child (Old and Young) we repeat the whole procedure with the remaining features and the remaining examples, until a stopping criterion is met.

## 3.7 Stopping criteria

Your notes list these explicitly:

1. **Node is 100% pure** -- all examples belong to one class, so entropy = 0 and there's nothing to gain.
2. **Maximum tree depth reached** -- the `max_depth` hyperparameter is set by the user to control overfitting.
3. **Information gain from a further split is below a threshold** -- even the best split barely helps.
4. **Number of examples in a node is below a threshold** -- splitting tiny nodes just fits noise.

Why do we need any stopping at all? Because a tree that is grown until every leaf is pure will **overfit**. It will memorise the training data and fail on new patients.

## 3.8 Handling continuous features (like weight)

Categorical features are easy: one branch per value. But what about *weight = 7.2 kg*?

**Procedure from your notes:**

1. **Sort** the numeric values for that feature.
2. **Midpoints** between consecutive sorted values are candidate thresholds. With n values you get n-1 midpoints.
3. For each candidate threshold t, construct the binary split `w <= t` vs `w > t`.
4. Compute information gain for each candidate.
5. Pick the threshold with the highest info gain. Use that threshold for the split.

**Example from your notes.** Weights sorted: 7.2, 8.4, 8.8, 9.2, 10.2, 11, 15, 18, 20. Nine midpoints. Checking threshold w <= 8:

- Left (<= 8): weights {7.2}, labels {1}. H(2/2) = 0.
- Right (> 8): remaining 9 items; the notes show p1 = 3/8 class split giving H(3/8).

Info gain for w <= 8:

$$\text{IG} = H(0.5) - \left(\tfrac{2}{10} H(0) + \tfrac{8}{10} H(3/8)\right) \approx 0.24$$

The threshold with the largest such gain becomes the split rule for the weight feature.

## 3.9 Handling categorical features with more than 2 values -- one-hot encoding

If Tumor_shape has three possible values {R, NR, Oval}, your notes' rule is:

> **Categorical with K values -> construct K binary features each taking 0 or 1.**

So "Tumor_shape = Oval" becomes its own new feature that is either 0 or 1. This is called **one-hot encoding**.

| Original | Shape_R | Shape_NR | Shape_Oval |
|----------|---------|----------|------------|
| R        | 1       | 0        | 0          |
| NR       | 0       | 1        | 0          |
| Oval     | 0       | 0        | 1          |

After one-hot encoding, every feature is binary and the normal decision-tree algorithm works as-is.

## 3.10 Second worked example from your notes -- Vaccination feature

Your notes also solve a different small dataset. The key numbers:

- 12 total examples. Initial entropy (of the target "Malignant") is computed as H(5/7) ≈ 0.86 when restricted to the vaccinated subgroup, and **0.9798** overall before splitting.
- After splitting on Vaccination, weighted children entropy = (5/12)(0) + (7/12)(0.86) ≈ 0.501
- Information gain = 0.9798 - 0.501 = **0.4788**

Again, the feature with the highest IG becomes the split.

## 3.11 Interpretability and ensembles

- **Decision tree = interpretable model.** A small tree is a readable set of if-then rules. In medicine this matters a lot.
- **Random Forest = ensemble of decision trees.** Many trees are trained on random subsets of data and features; they vote. More accurate but less interpretable.

## 3.12 Short questions

1. Define entropy. Why is it used instead of raw error rate for splitting?
2. State the information gain formula in your own words.
3. Why does pruning (or setting max_depth) help decision trees generalize?
4. Give two stopping criteria for growing a decision tree.
5. How are continuous features handled when choosing a split?

---
---

# CHAPTER 4 -- DECISION TREES FOR REGRESSION

## 4.1 What changes when the target is a number?

So far the target was a class (0 or 1). What if the target is a real number -- tumor weight, survival days, gene expression level? We still use a decision tree, but two things change:

1. **Leaf prediction** is no longer a class vote. It is the **average of the target values** among the training examples that fall into that leaf.
2. **Splitting criterion** is no longer information gain. It is **reduction in variance.**

## 4.2 Variance as impurity

For regression we want leaves where the target values are *tightly clustered*. That is measured by variance:

$$\text{Var}(S) \;=\; \frac{1}{|S|} \sum_{x \in S} \left(x - \bar{S}\right)^{2}$$

Low variance = target values are all similar = good leaf. High variance = all over the place = bad leaf.

## 4.3 Reduction in variance -- the splitting rule

$$\boxed{\; \Delta \text{Var} \;=\; \text{Var}(\text{before split}) \;-\; \sum_{v} \frac{|S_v|}{|S|} \text{Var}(S_v) \;}$$

We pick the feature that **maximises** this variance reduction. This is the direct analog of information gain, with variance replacing entropy.

## 4.4 Worked example from your notes -- Weight regression

Dataset of 10 patients with target = weight. Splitting on Age:

- **Old** group weights: 7.2, 9.2, 8.4, 7.6, 10.2 -> Variance = **1.47**
- **Young** group weights: 8.8, 15, 18, 18, 20 -> Variance = **21.87**

Variance of the full set before splitting: **20.5**

Weighted children variance:

$$\tfrac{5}{10}(1.47) + \tfrac{5}{10}(21.87) = 0.735 + 10.935 = 11.67$$

Reduction in variance:

$$\Delta\text{Var} = 20.5 - 11.67 \;\approx\; 8.84$$

(Your notes round this as 8.84.) The splitter tries every feature this way and picks the one with the highest variance drop.

Notice how the Young group has huge variance (21.87) because 8.8 is next to 20. If another feature could cleanly separate those two, it would win the comparison.

## 4.5 Leaf prediction

At a leaf, the predicted value is simply the **mean** of the training targets that landed there. So if Old-R-Light samples have weights {7.2, 8.4, 7.6, 10.2}, a new old-R-light patient would be predicted weight = (7.2+8.4+7.6+10.2)/4 ≈ 8.35 kg.

## 4.6 Short questions

1. Why is variance (not entropy) the right impurity for regression trees?
2. How is the predicted value at a regression leaf computed?
3. In the Age example, why does the Young branch have much higher variance than Old?

---
---

# PART II -- LINEAR ALGEBRA FOR BIOINFORMATICS

# CHAPTER 5 -- VECTORS, BASIS, LINEAR INDEPENDENCE, EIGENVECTORS

Before we can talk about PCA (next chapter) we need the linear-algebra vocabulary your notes use.

## 5.1 What does "a matrix hits a vector" mean?

If you multiply a matrix A by a vector x, you get a new vector Ax. **Almost always that new vector points in a different direction** than x. Your notes make this point pictorially: A stretches, squeezes, rotates, or reflects x.

Example: A = [[1, 1], [2, 0]], x = [1, 3]. Then Ax = [1·1 + 1·3, 2·1 + 0·3] = [4, 2]. The direction changed: x was tilted up-right, Ax is tilted down-right.

## 5.2 Eigenvectors -- the special directions that don't get rotated

For a square matrix A there exist special vectors x that, when hit by A, come out pointing in **the same direction** -- only scaled. These are the **eigenvectors**.

$$\boxed{\; A\mathbf{x} \;=\; \lambda \mathbf{x} \;}$$

- **x** = eigenvector (non-zero vector)
- **λ** (lambda) = eigenvalue (a scalar)

Interpretation: A acts on the eigenvector by simply multiplying its length by λ. Negative λ means it flips. λ = 1 means the vector is totally unchanged.

Every square n × n matrix has at most n linearly independent eigenvectors. For symmetric matrices, those eigenvectors are **orthogonal** -- this fact is what makes PCA work (we will use it in chapter 6).

## 5.3 Linear independence

A set of vectors {v1, v2, ..., vn} is **linearly independent** if no vector in the set can be written as a linear combination of the others. Equivalently, the only scalars c1, ..., cn that satisfy

$$c_1 \mathbf{v}_1 + c_2 \mathbf{v}_2 + \cdots + c_n \mathbf{v}_n = \mathbf{0}$$

are c1 = c2 = ... = cn = 0. Any nonzero solution means the vectors are **linearly dependent**.

### Example from your notes

Let v1 = [1, 2]^T, v2 = [3, -5]^T in R^2. Check independence:

$$c_1 \begin{bmatrix} 1 \\ 2 \end{bmatrix} + c_2 \begin{bmatrix} 3 \\ -5 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$$

Two equations:
- c1 + 3c2 = 0
- 2c1 - 5c2 = 0

From the first, c1 = -3c2. Substitute: 2(-3c2) - 5c2 = -6c2 - 5c2 = -11c2 = 0, so c2 = 0, hence c1 = 0. **Linearly independent.**

## 5.4 Basis of R^n

A **basis** of R^n is a set of n vectors that are (i) linearly independent and (ii) span the whole space -- every vector in R^n can be written as a linear combination of them.

**The canonical basis of R^2** is {[1,0]^T, [0,1]^T}, but there are infinitely many others; any two linearly independent 2-vectors form a basis.

Key fact used in PCA: **any n linearly independent vectors in R^n form a basis.**

## 5.5 Orthogonal and orthonormal

- **Orthogonal**: two vectors are perpendicular, i.e. their dot product is zero.
- **Orthonormal**: orthogonal AND each has unit length (|| v || = 1).

An orthonormal basis is the "cleanest" possible basis. PCA will build one such basis out of eigenvectors of the covariance matrix.

## 5.6 Short questions

1. Define eigenvector and eigenvalue.
2. What does it mean for a matrix to "preserve the direction" of its eigenvector?
3. Prove that [1,2] and [3,-5] in R^2 are linearly independent.
4. Why do we specifically care about *symmetric* matrices in PCA?

---
---

# CHAPTER 6 -- PRINCIPAL COMPONENT ANALYSIS (PCA)

## 6.1 The bioinformatics motivation

Microarray data has thousands of genes (dimensions) per sample but only tens of samples. Visualising it or running classifiers on it is a nightmare. PCA finds a small set of *new* axes along which almost all the variation lives, letting us throw away the low-variance directions.

## 6.2 The two goals of PCA (from your notes)

1. **Along the new axes, the data should have high variance.** Variance = information, so you want it.
2. **The new axes should be uncorrelated (linearly independent).** Even better, **orthogonal**.

That's the whole brief. Now we turn it into a procedure.

## 6.3 Setup and notation

- We have m data points x1, x2, ..., xm in R^n (each is an n-dimensional column).
- Stack them as rows into a matrix X of shape (m × n).

**Step 0 -- Centering (zero mean).** Subtract each column's mean from that column so every column of X has mean 0. Your notes call this "making the data 0 mean" or *standardization / scaling*.

$$x_{ij} \;\leftarrow\; x_{ij} - \mu_j \quad \text{for every column } j$$

This step is essential: PCA measures variance about the origin, so we must move the data so the origin is the mean.

## 6.4 The new basis

Let v1, v2, ..., vn be a set of orthonormal vectors in R^n (these will turn out to be eigenvectors of the covariance matrix, but for now just assume we have them). Assemble them as columns of an n × n matrix

$$P = \big[\, \mathbf{v}_1 \,|\, \mathbf{v}_2 \,|\, \ldots \,|\, \mathbf{v}_n \,\big]$$

**Representing a data point in the new basis.** A single point xi (a row of X) is expressed as

$$x_i = c_{i1} \mathbf{v}_1 + c_{i2} \mathbf{v}_2 + \ldots + c_{in} \mathbf{v}_n$$

where each coefficient is

$$c_{ij} \;=\; x_i^{T} \mathbf{v}_j$$

Stacking for all samples, the transformed dataset is

$$\boxed{\; \hat{X} \;=\; X P \;}$$

which has the same shape (m × n) as the original.

**Theorem from your notes.** If X's columns have zero mean and X̂ = XP, then the columns of X̂ also have zero mean. (Translation: the centering is preserved under the linear change of basis.)

## 6.5 Where does P come from? The covariance matrix

We want new axes where the data is **uncorrelated**. In the original basis, the covariance matrix of X is

$$\Sigma \;=\; \frac{1}{m}\, X^{T} X \quad \text{(since X is already centered)}$$

Σ is an **n × n square symmetric matrix**. Its entries:

$$\Sigma_{ij} \;=\; \frac{1}{m} \sum_{k=1}^{m} (x_{ki} - \mu_i)(x_{kj} - \mu_j) \;=\; \frac{1}{m}\, x_i^{T} x_j$$

- Diagonal entries Σii are **variances** of each feature.
- Off-diagonal entries Σij are **covariances** between features i and j.

**The ideal covariance matrix** after PCA looks like

$$\Sigma \;=\; \begin{bmatrix} \text{Var}(x) & 0 \\ 0 & \text{Var}(y) \end{bmatrix}$$

because off-diagonals (covariances) are zero -- the new axes are uncorrelated, which is what we asked for.

## 6.6 The key fact that solves PCA

Σ is square and symmetric. **The eigenvectors of a square symmetric matrix are orthogonal.** So if we choose P to be the matrix whose columns are the eigenvectors of Σ, then:

- The new basis is automatically orthonormal (after normalising each eigenvector to unit length).
- In the new basis, the covariance matrix of X̂ = XP is **diagonal**, with the eigenvalues of Σ on the diagonal -- i.e. the features are uncorrelated and the variance along vj is exactly λj.

This is the payoff. PCA = "rotate the data to the eigen basis of its covariance matrix".

## 6.7 The PCA algorithm in 6 steps

1. Arrange data as rows of an (m × n) matrix X.
2. **Center** X: subtract column means so each feature has mean 0.
3. Compute the **covariance matrix** Σ = (1/m) X^T X  (shape n × n).
4. Compute **eigenvectors** v1, v2, ..., vn and **eigenvalues** λ1 ≥ λ2 ≥ ... ≥ λn of Σ.
5. Form P by stacking the top k eigenvectors as columns (k is how many dimensions you want to keep).
6. Project: **X̂ = X P**  (shape m × k). This is your reduced data.

## 6.8 How many components to keep?

The eigenvalue λj is *exactly* the variance captured by component j. A common heuristic: keep the smallest k such that

$$\frac{\lambda_1 + \lambda_2 + \ldots + \lambda_k}{\lambda_1 + \lambda_2 + \ldots + \lambda_n} \;\geq\; 0.95$$

i.e. 95% of the total variance. You can set other thresholds (90%, 99%) depending on the application.

## 6.9 Intuition summary

- PCA is linear algebra applied to statistics. It finds the directions that matter.
- "Direction" = eigenvector. "Matters" = eigenvalue (= variance along that direction).
- We keep only the top few eigenvectors. In bioinformatics, this turns 20 000 genes into 2-10 usable components for visualisation and downstream ML.

## 6.10 Short questions

1. Why must the data be centered before computing the covariance matrix?
2. What does an eigenvalue of the covariance matrix physically represent?
3. State why the eigenvectors of Σ are guaranteed to be orthogonal.
4. If λ1 = 50, λ2 = 10, λ3 = 4, λ4 = 1, what fraction of variance is captured by the first two components? *(Answer: 60/65 ≈ 0.923 = 92.3%.)*

---
---

# PART III -- MEDICAL IMAGING INFORMATION SYSTEMS

# CHAPTER 7 -- PACS (PICTURE ARCHIVAL AND COMMUNICATION SYSTEM)

## 7.1 What problem is PACS solving?

Modern hospitals generate mountains of medical images every day:

- A single CT scanner does roughly **50 scans a day** (your notes).
- A calibrated MRI system does about **22 scans a day** (your notes). *(These numbers are "operational dependent" -- they change with hospital size and equipment.)*
- Each scan is a big file. CT uses **Hounsfield Units** (the notes write "Houston" which is a misspelling) on a range of roughly -2000 to +3000.
- Radiological images/videos are typically **10 bits per pixel** (for clinical grayscale), though *ordinary* grayscale is 8 bits.

Before PACS, these images were printed on film. Finding an old scan meant digging through physical archives. Sharing one meant walking the film down the hall. PACS digitizes all of that.

**PACS** = **P**icture **A**rchival and **C**ommunication **S**ystem.

## 7.2 Role of PACS

PACS stores two things *together*, linked to each image:

1. **Clinical details** -- patient ID, notes, etc.
2. **Radiological report** -- what the radiologist saw and concluded.

Both are stored as **metadata** attached to the digital image. Regulation in many countries requires these images to be retained for **10 to 20 years**, so storage is no joke.

## 7.3 The PACS workflow

```
Imaging device  ->  Acquisition computer  ->  Gateway / router  ->  PAC server
 (CT, MRI,                                                           |
  X-ray, USG)                                                        v
                                                           Secondary storage
                                                           (10-20 years)
                                                                     |
                                                                     v
                                                              Report room
                                                          (separate from
                                                           acquisition room)
```

Key points:

- **Report room is physically separate from the acquisition room.** Radiologists read images in a quiet, dim environment, not in the middle of a busy scanner bay.
- In **some countries (e.g. the US)**, **voice-over reports** are added to the data -- the radiologist dictates findings into the record.
- Modern PACS architectures include **AI modules for image pre-processing** (denoising, auto-segmentation, triage).

## 7.4 The three hospital information systems that talk to PACS

| System | Full name | What it does |
|---|---|---|
| **HIS** | Hospital Information System | The *master* system. Manages all patient entry, demographics, basic patient data. Every patient gets a **Unique Patient ID** here. (Sometimes written HIMS = Hospital Information *Management* System.) |
| **RIS** | Radiology Information System | Specific to the radiology department. Gets patient info from HIS, manages the modality work-lists ("patient X needs an MRI of the knee"), tracks report status. |
| **PACS** | Picture Archival & Communication System | Stores the images themselves (plus metadata) and delivers them to workstations. |

These three systems are connected through **bidirectional integration**. Patient demographic data is entered **only once** (in HIS) and flows automatically to RIS and PACS. This avoids mistakes and duplicate data entry.

```
       HIS
       / \
      v   v
   PACS <-> RIS
```

## 7.5 Subsystems of PACS (the 5 subsystems)

Your notes say PACS has **5 subsystems**. Here they are:

1. **Image acquisition subsystem** -- interfaces with CT, MRI, X-ray, ultrasound to pull images off the modality.
2. **PAC server** -- central broker that receives, indexes, and dispatches images.
3. **Display / Review workstations** -- the monitors radiologists and physicians use to view images. *Display workstations* are for initial reading; *review workstations* are for everyone else.
4. **Database / storage subsystem (DBMS)** -- short-term, medium-term, and long-term storage (see next section).
5. **Communication network** -- LAN (hospital internal), and a telemedicine port for outside connections (see 7.7).

## 7.6 Storage architecture -- three tiers

Designing a PAC system requires **three storage structures**. Which ones you buy decides the architecture and cost of the whole system.

| Tier | Speed | Technology | Purpose |
|---|---|---|---|
| **Short term** | Very fast | **SSD** + **RAID** configuration | Recently acquired images that are being actively viewed or reported on |
| **Medium term** | Moderate | Hard disks / spinning storage | Patients who might come back next week or next month |
| **Long term** (LTA) | Slow, cheap | **Magnetic tape** | Years-old images kept for legal compliance |

**RAID at the short-term tier.** RAID stands for Redundant Array of Independent Disks. It gives you:

- **Redundancy** of data -- typically 2x redundancy (data stored on two drives). If one drive dies, the other has the copy.
- **Distributed copies** -- data is stored in 5 or 6 different places so there is *always* a backup.
- **Fast reads** since multiple drives can serve data in parallel.

**SSDs** are used where you need very fast memory (display workstations, active work). **Magnetic tape** is for long-term archive because it is dirt-cheap per terabyte.

```
  Image acquisition
         |
         v
   Short-term server (SSD + RAID)
      |          |        |
      v          v        v
    LTA         Web    Workstation
  (tape)
```

## 7.7 PACS architecture -- LAN vs WAN vs telemedicine port

- **Inside the hospital**, PACS runs over a **LAN** (local area network). LAN is fast and private.
- **Across hospitals or for remote consultation**, you do *not* expose PACS to the open **WAN**. Instead, a **Telemedicine Port** is used. It is a controlled gateway that:
  - Does **not** transmit sensitive identifiable info.
  - Excludes items like patient surgical video data by default.
- **Patient surgical video** is pushed *into* PACS over the LAN, and **only the annotations and post-processing results** are pushed back out -- not the raw video.

## 7.8 Centralised vs Distributed PACS

### Centralised PACS
- All storage and processing at **one central site**.
- Works fine for small hospitals (short-term storage only).
- **Does not scale** to big hospitals -- network bandwidth and single point of failure become problems.

### Distributed PACS
- Developed by **Mayo Clinic**.
- Runs **65 MRI scan flows across the US** (according to your notes).
- Architecture: separate **MR cluster**, **CT cluster**, **CR cluster** (computed radiography) each storing their own modality's data, **all connected by a fibre optic network**. The final data is pushed to a long-term archive cluster.
- Separate DBMS manages the index.

**Disadvantages of distributed PACS**:

- **Expensive**, complex technology.
- **Maintenance programme** required continually.
- **Dedicated personnel** (sysadmins, network engineers, radiographers) are mandatory.
- **No simple fall-back** if the fibre optic network fails; a conventional film-based alternative is hard to reinstate.

## 7.9 DDR -- Direct Digital Radiography (the sensor chain)

Your notes sketch two chains for converting X-rays into digital images:

### Indirect DDR (most common clinical X-ray)
```
X-ray -> CsI (caesium iodide scintillator) -> Amorphous silicon panel -> Read-out electronics -> Digital signal
```
The X-ray is first converted to *light* by the scintillator, then that light hits the amorphous silicon photo detectors, which output electrons, then read-out electronics digitise the signal.

### Direct DDR
```
X-ray -> Selenium (amorphous silicon panel) -> Read-out electronics -> Digital signal
```
The X-ray is converted *directly* into electrons by the selenium layer, skipping the light step. This gives sharper images because you don't get "light spread" in the phosphor layer.

## 7.10 PACS workstations

- **Display workstation** -- high-resolution calibrated monitors for the radiologist doing the primary read. Colour calibration and consistent luminance matter, because subtle grey differences can be a diagnosis.
- **Review workstation** -- lower-spec, for physicians, residents, and other staff to look at images after the report is filed.

## 7.11 Short questions

1. What is PACS? What are its five subsystems?
2. Differentiate HIS, RIS, and PACS.
3. Explain the three-tier storage architecture and why each tier uses a different technology.
4. Why is a telemedicine port used instead of a raw WAN connection?
5. Contrast centralised and distributed PACS. Which is used by Mayo Clinic?
6. Describe the direct and indirect DDR signal chains.
7. Why must the report room be separated from the acquisition room?
8. What is RAID and why is 2x redundancy used in PACS?

---
---

# CHAPTER 8 -- DICOM AND MEDICAL IMAGE COMPRESSION

## 8.1 DICOM -- what and why

**DICOM** stands for **Digital Imaging and Communications in Medicine**. It is the universal standard for **handling, storing, printing and transmitting** medical images. Every CT scanner, MRI scanner, PACS server, and workstation on Earth speaks DICOM.

A DICOM file is not *just* an image. It is an image **plus a header** full of patient, study, series, and device metadata (name, DOB, modality, acquisition parameters, orientation, slice thickness, etc.). All of that travels with the pixels.

## 8.2 Why DICOM exists (from your notes)

1. **Workflow management** -- preparation of **worklists** in a sequential order. A technologist reads off the worklist to know which patient to scan next. Without DICOM, each vendor would invent their own worklist format.
2. **Indication about image quality** -- the standard lets scanners tag images so doctors know whether a study is usable, blurred, artefact-heavy, etc.
3. **Vendor interoperability** -- a Siemens CT, a GE MRI, and a Philips PACS all understand each other because they all implement DICOM.

## 8.3 Medical image compression -- JPEG and wavelets

Radiological images are large (a chest CT can be several hundred megabytes). You cannot store or send them raw forever -- you must compress them. But medical compression is different from compressing a cat photo: you cannot afford to lose diagnostic information.

### JPEG with wavelets
Classical JPEG uses a Discrete Cosine Transform; modern medical pipelines use **wavelets** instead. A wavelet transform splits the image into **low-frequency** components (big structural shapes -- the organs) and **high-frequency** components (tiny variations -- mostly noise and edges). You can compress the noise aggressively and the structure lightly.

### Psychoacoustic (psychoperceptual) compression
Your notes note that the **same mechanism used in hearing aids** (psycho-acoustic compression: keep only the 300 Hz to 6 kHz band that matters for speech) is analogous to what JPEG does for images:

1. Separate image into **high and low frequency** components (using a Fourier/wavelet transform).
2. **Amplify low frequency** (structural data the doctor cares about).
3. **Suppress high frequency** (noise the doctor does not need).

In hearing aids you throw away frequencies outside 300 Hz - 6 kHz because the human speech channel lives there. In medical image compression you throw away high-frequency image noise because diagnosis lives in the mid-to-low spatial frequencies.

## 8.4 Bit depth in medical images

- **Normal grayscale images**: 8 bits per pixel -> 256 grey levels.
- **Medical grayscale (CT, MRI, X-ray)**: **10 bits per pixel** -> 1024 grey levels.

The extra grey levels matter because clinical features can differ by just a few units of intensity and would be invisible at 8 bits.

## 8.5 Hounsfield units (CT specific)

CT numbers are reported in **Hounsfield Units (HU)**. Typical range: about **-1000 (air)** to **+3000 (dense bone / metal)**. Water is defined as 0 HU. The formula is

$$\text{HU} \;=\; 1000 \times \frac{\mu - \mu_{\text{water}}}{\mu_{\text{water}}}$$

where μ is the linear X-ray attenuation coefficient of the tissue at that voxel. Your notes write this as "2000 to 3000 Houston units" -- "Houston" is a misreading of "Hounsfield". The unit is named after Godfrey Hounsfield, inventor of the CT scanner.

## 8.6 Short questions

1. What does DICOM stand for? What does it include beyond pixels?
2. Why do hospitals need DICOM?
3. Why are wavelets preferred over plain DCT for medical image compression?
4. How is psychoacoustic compression analogous to frequency-domain image compression?
5. Why do medical images use 10-bit pixels instead of 8-bit?
6. What is a Hounsfield unit?

---
---

# PART IV -- FULLY SOLVED EXAM-STYLE NUMERICAL PROBLEMS

These are modelled on the exact computations in your notes. Every arithmetic step is shown.

## Problem 1 -- Naive Bayes classification

Using the 10-row tumor dataset (Chapter 1.5), classify the new sample **X = {Small, Old}**.

**Solution.**

Priors: P(B) = 7/10 = 0.7, P(M) = 3/10 = 0.3.

Feature counts among B (rows 1,2,3,4,6,7,8):
- Small: rows 2,3,6,8 -> 4/7
- Old: rows 2,4,6,7 -> 4/7

Feature counts among M (rows 5, 9, 10):
- Small: rows 9,10 -> 2/3
- Old: row 9 -> 1/3

Naive Bayes scores:
- P(B | X) ∝ 0.7 × (4/7) × (4/7) = 0.7 × 16/49 ≈ 0.2286
- P(M | X) ∝ 0.3 × (2/3) × (1/3) = 0.3 × 2/9 ≈ 0.0667

**Since 0.2286 > 0.0667, classify X = {Small, Old} as Benign.**

## Problem 2 -- Bayesian network joint probability

Using the 4-node network from Chapter 2.6, compute **P(A=1, B=0, C=1, D=1)**.

**Solution.**

$$P(A{=}1, B{=}0, C{=}1, D{=}1) = P(A{=}1)\,P(B{=}0)\,P(C{=}1 \mid A{=}1, B{=}0)\,P(D{=}1 \mid C{=}1)$$

Plug in:

- P(A=1) = 0.8
- P(B=0) = 0.6
- P(C=1 | A=1, B=0) = 0.7
- P(D=1 | C=1) = 0.3

$$= 0.8 \times 0.6 \times 0.7 \times 0.3 \;=\; 0.1008$$

## Problem 3 -- Entropy

A node contains 8 examples with labels: 1, 1, 1, 1, 0, 0, 0, 0. Compute its entropy.

**Solution.**

p1 = 4/8 = 0.5, p0 = 0.5.

$$H = -0.5 \log_2(0.5) - 0.5 \log_2(0.5) = -0.5(-1) - 0.5(-1) = 1.0$$

Maximum entropy -- this node is completely impure.

## Problem 4 -- Information gain

Parent node has entropy H(parent) = 0.94. After splitting on feature F, the two children have sizes 6 and 4 with entropies 0.65 and 0.0 respectively. Compute IG.

**Solution.**

$$\text{Weighted avg} = \tfrac{6}{10}(0.65) + \tfrac{4}{10}(0.0) = 0.39 + 0 = 0.39$$

$$\text{IG} = 0.94 - 0.39 = 0.55$$

## Problem 5 -- Variance reduction for regression tree

Variance before splitting = 25.0. After splitting on Age, the two children have sizes 5 and 5 with variances 2.0 and 8.0. Compute the variance reduction.

**Solution.**

$$\text{Weighted child var} = \tfrac{5}{10}(2.0) + \tfrac{5}{10}(8.0) = 1.0 + 4.0 = 5.0$$

$$\Delta\text{Var} = 25.0 - 5.0 = 20.0$$

## Problem 6 -- Total probability / Bayes flip

In a diagnostic setting, P(disease) = 0.02, P(+ | disease) = 0.98, P(+ | no disease) = 0.05. Compute P(disease | +).

**Solution.**

First compute the denominator:

$$P(+) = P(+\mid D) P(D) + P(+\mid \lnot D) P(\lnot D)$$
$$= 0.98 \times 0.02 + 0.05 \times 0.98 = 0.0196 + 0.049 = 0.0686$$

Then:

$$P(D\mid +) = \frac{0.98 \times 0.02}{0.0686} = \frac{0.0196}{0.0686} \approx 0.2857$$

Roughly **28.6%**. This is the famous base-rate fallacy -- a "positive" result on a highly accurate test still doesn't mean the patient probably has the disease, because the disease is rare.

## Problem 7 -- Eigenvector check

Let A = [[2, 0], [0, 3]]. Is v = [1, 0]^T an eigenvector? What is its eigenvalue?

**Solution.**

$$A\mathbf{v} = \begin{bmatrix} 2 & 0 \\ 0 & 3 \end{bmatrix}\begin{bmatrix} 1 \\ 0 \end{bmatrix} = \begin{bmatrix} 2 \\ 0 \end{bmatrix} = 2 \begin{bmatrix} 1 \\ 0 \end{bmatrix} = 2 \mathbf{v}$$

**Yes**, v is an eigenvector with eigenvalue **λ = 2**.

## Problem 8 -- PCA variance captured

Eigenvalues of the covariance matrix of a dataset are λ1 = 8, λ2 = 4, λ3 = 2, λ4 = 1. If we keep the top two principal components, what fraction of variance is retained?

**Solution.**

Total variance = 8 + 4 + 2 + 1 = 15.

Variance captured by top 2 = 8 + 4 = 12.

Fraction = 12/15 = 0.8 = **80%**.

---
---

# PART V -- MCQ BANK A: THEORETICAL MULTIPLE-CHOICE

Write your answers on a separate sheet. Answer key at the end.

---

**Q1.** In Bayes' theorem P(C | X) = P(C) · P(X | C) / P(X), the term P(C) is called:
(a) Posterior
(b) Prior
(c) Likelihood
(d) Evidence

**Q2.** The "naive" assumption in a Naive Bayes classifier is that:
(a) All classes are equally likely
(b) Features are conditionally independent given the class
(c) The prior is always uniform
(d) The features are all binary

**Q3.** A Bayesian belief network is:
(a) An undirected cyclic graph
(b) A directed cyclic graph
(c) A directed acyclic graph
(d) An undirected bipartite graph

**Q4.** In a BBN, the joint probability factorises as:
(a) Sum of conditional probabilities on each node
(b) Product of P(node | all other nodes)
(c) Product of P(node | parents of that node)
(d) Product of marginal probabilities of each node

**Q5.** The maximum value of binary entropy H(p1) is attained at:
(a) p1 = 0
(b) p1 = 0.25
(c) p1 = 0.5
(d) p1 = 1.0

**Q6.** Information gain is defined as:
(a) Entropy of the children minus entropy of the parent
(b) Entropy of the parent minus weighted average of children entropies
(c) Sum of children entropies
(d) Product of children entropies

**Q7.** Which of the following is NOT a valid stopping criterion for a decision tree?
(a) Node is 100% pure
(b) Maximum depth reached
(c) Information gain below a threshold
(d) Training accuracy reaches 50%

**Q8.** In a regression tree, the splitting criterion is:
(a) Information gain
(b) Gini impurity
(c) Reduction in variance
(d) Maximum likelihood

**Q9.** The depth of the root node in a decision tree is:
(a) 0
(b) 1
(c) -1
(d) Equal to the number of features

**Q10.** A decision tree is called an "interpretable model" because:
(a) It is fast to train
(b) Its rules can be read off directly as if-then statements
(c) It always has 100% accuracy
(d) It uses only linear algebra

**Q11.** Random Forest is:
(a) A single deep decision tree
(b) An ensemble of decision trees
(c) A neural network
(d) A Bayesian network

**Q12.** For a square symmetric matrix, the eigenvectors are:
(a) Always parallel
(b) Always orthogonal
(c) Always equal
(d) Always zero

**Q13.** In the eigenvalue equation A·x = λx, what does λ represent?
(a) A new vector
(b) The scalar by which the eigenvector is stretched
(c) The determinant of A
(d) The inverse of A

**Q14.** A set of n vectors is linearly independent if:
(a) They are all the same
(b) No vector can be written as a linear combination of the others
(c) They have the same length
(d) Their sum is zero

**Q15.** The first step in PCA is:
(a) Computing eigenvalues of the raw data
(b) Centering the data so each feature has zero mean
(c) Normalising features to unit length
(d) Computing the SVD of the transpose

**Q16.** The covariance matrix Σ used in PCA has shape:
(a) m × m (number of samples squared)
(b) n × n (number of features squared)
(c) m × n
(d) 1 × n

**Q17.** The diagonal entries of the covariance matrix represent:
(a) Means of the features
(b) Variances of the features
(c) Covariances between features
(d) Eigenvalues

**Q18.** After applying PCA, the ideal covariance matrix of the transformed data should be:
(a) All zeros
(b) Diagonal (off-diagonals are zero)
(c) Full with equal entries
(d) Triangular

**Q19.** In PCA, the eigenvalue of a component equals:
(a) The mean of that component
(b) The variance captured by that component
(c) The length of the eigenvector
(d) Zero

**Q20.** PACS stands for:
(a) Patient Access Control System
(b) Picture Archival and Communication System
(c) Personal Archive Clinical System
(d) Primary Acquisition Control Station

**Q21.** Which of the following is NOT one of the five PACS subsystems?
(a) Image acquisition
(b) PAC server
(c) Display / review workstation
(d) Laboratory information manager

**Q22.** HIS, RIS and PACS are connected by:
(a) Unidirectional integration
(b) Bidirectional integration
(c) No integration (they are isolated)
(d) A shared filesystem only

**Q23.** Patient demographic data in a modern hospital is entered:
(a) Separately in every system
(b) Once in HIS and propagated to RIS and PACS
(c) By the radiologist during reporting
(d) By the PACS administrator

**Q24.** Which storage tier in PACS typically uses magnetic tape?
(a) Short term
(b) Medium term
(c) Long term archive (LTA)
(d) Cache

**Q25.** RAID configuration in short-term PACS storage provides:
(a) Faster rendering of images
(b) Redundancy of data and distributed copies
(c) Compression of images
(d) Encryption of metadata

**Q26.** For long-distance access to PACS between hospitals, the preferred connection is:
(a) A direct WAN link with full patient data
(b) A Telemedicine Port that excludes sensitive info
(c) Internet via public VPN
(d) Courier with USB drives

**Q27.** Distributed PACS was developed by:
(a) Siemens
(b) GE Healthcare
(c) Mayo Clinic
(d) Philips

**Q28.** Most radiological images are encoded at:
(a) 8 bits per pixel
(b) 10 bits per pixel
(c) 16 bits per pixel
(d) 24 bits per pixel

**Q29.** CT intensities are measured in:
(a) Hertz
(b) Hounsfield units
(c) Grays
(d) Sieverts

**Q30.** In indirect DDR, the X-ray is first converted into:
(a) Heat
(b) Light by a scintillator (CsI)
(c) Sound
(d) Electric current directly

**Q31.** DICOM stands for:
(a) Digital Imaging and Communications in Medicine
(b) Direct Image Communication over the Medical network
(c) Distributed Image Control and Management
(d) Diagnostic Information and Clinical Operations Model

**Q32.** Why are wavelets preferred over DCT for medical image compression?
(a) They are faster
(b) They separate image into low and high frequency components, preserving structure while suppressing noise
(c) They need less memory
(d) They work without any transform

**Q33.** The disadvantages of distributed PACS include all EXCEPT:
(a) Expensive technology
(b) Maintenance programme required
(c) Dedicated personnel required
(d) Inability to handle more than 10 patients

**Q34.** A "display workstation" in PACS is used primarily by:
(a) Hospital administrators
(b) The primary radiologist reading the scans
(c) Patients reviewing their own reports
(d) Insurance providers

**Q35.** The acyclic property of a Bayesian network ensures that:
(a) There are no leaf nodes
(b) Probabilities do not reference themselves through a loop
(c) All nodes are binary
(d) Every node has exactly one parent

---

# PART V (continued) -- MCQ BANK B: NUMERICAL MULTIPLE-CHOICE

Use a calculator or log2 table as needed. log2(0.5)=-1, log2(0.25)=-2, log2(0.2)≈-2.32, log2(0.8)≈-0.32, log2(0.75)≈-0.415, log2(0.33)≈-1.585, log2(0.67)≈-0.585.

---

**Q36.** Given P(D1) = 0.4, P(S1|D1) = 0.3, P(S1|D1') = 0.6, what is P(S1)?
(a) 0.36
(b) 0.42
(c) 0.48
(d) 0.54

**Q37.** For the 4-node BBN (Chapter 2.6) compute P(A=0, B=0, C=1, D=0).
(a) 0.0096
(b) 0.0168
(c) 0.0672
(d) 0.0840

*(Work: P(A=0)·P(B=0)·P(C=1|0,0)·P(D=0|C=1) = 0.2 · 0.6 · 0.8 · 0.7 = 0.0672.)*

**Q38.** Using the 5-variable student network: P(l=1|g=1)=0.8, P(s=1|i=1)=0.8, P(g=1|i=1,d=1)=0.5, P(i=1)=0.4, P(d=1)=0.4. Then P(i=1, d=1, g=1, s=1, l=1) =
(a) 0.0256
(b) 0.0512
(c) 0.1024
(d) 0.2048

**Q39.** A node has 10 examples: 6 positive, 4 negative. Its entropy is closest to:
(a) 0.722
(b) 0.881
(c) 0.971
(d) 1.000

*(p1=0.6, H = -(0.6)log2(0.6) - (0.4)log2(0.4) ≈ 0.442 + 0.529 = 0.971.)*

**Q40.** If the parent entropy is 1.0 and splitting on feature F gives two children with sizes 4 and 6 and entropies 0.0 and 0.918 respectively, the information gain is:
(a) 0.082
(b) 0.449
(c) 0.551
(d) 0.918

*(Weighted avg = 0.4·0 + 0.6·0.918 = 0.551. IG = 1.0 - 0.551 = 0.449.)*

**Q41.** Using the Chapter 3 numbers, the information gain from splitting on Age was:
(a) 0.038
(b) 0.116
(c) 0.280
(d) 0.720

**Q42.** Weighted average entropy after splitting on Color in the Chapter 3 dataset is closest to:
(a) 0.720
(b) 0.884
(c) 0.962
(d) 1.000

**Q43.** Variance before split = 20.5. Children have sizes 5 and 5 with variances 1.47 and 21.87. The reduction in variance is closest to:
(a) 2.74
(b) 8.84
(c) 11.67
(d) 15.42

**Q44.** P(X|Y=0)=0.01, P(X|Y=1)=0.03, P(Y=0)=P(Y=1)=0.5. Then P(Y=1|X) =
(a) 0.25
(b) 0.33
(c) 0.50
(d) 0.75

**Q45.** Disease prior P(D)=0.02, P(+|D)=0.98, P(+|D')=0.05. Then P(D|+) ≈
(a) 0.98
(b) 0.72
(c) 0.50
(d) 0.286

**Q46.** For 10 tumor examples, P(B)=7/10 and P(M)=3/10. If P(Big|B)=3/7, P(Young|B)=2/7, P(Big|M)=1/3, P(Young|M)=1/3, which class gets X = {Big, Young}?
(a) Benign, score ≈ 0.086
(b) Malignant, score ≈ 0.033
(c) Benign, score ≈ 0.029
(d) Malignant, score ≈ 0.200

**Q47.** A dataset has eigenvalues λ = (10, 6, 3, 1). The fraction of variance captured by the first two components is:
(a) 60%
(b) 75%
(c) 80%
(d) 90%

*(16 / 20 = 0.80.)*

**Q48.** Eigenvalues are (50, 30, 15, 5). To retain at least 95% of variance, you must keep at least how many components?
(a) 1
(b) 2
(c) 3
(d) 4

*(cumulative: 50/100=0.5, 80/100=0.8, 95/100=0.95 at k=3.)*

**Q49.** For A = [[3, 0], [0, 5]], which of the following is an eigenvector?
(a) [1, 0]^T with λ = 3
(b) [1, 1]^T with λ = 4
(c) [0, 0]^T with λ = 0
(d) [1, 2]^T with λ = 5

**Q50.** If a CT scanner does roughly 50 scans per day and each scan is 500 MB, the daily storage need is:
(a) 2.5 GB
(b) 10 GB
(c) 25 GB
(d) 50 GB

*(50 · 500 MB = 25 000 MB = 25 GB.)*

**Q51.** Binary entropy H(0.9) is closest to:
(a) 0.13
(b) 0.33
(c) 0.47
(d) 0.71

*(-(0.9)(-0.152)-(0.1)(-3.32) ≈ 0.137+0.332 ≈ 0.469.)*

**Q52.** A node with labels {1,1,1,1,1} has entropy equal to:
(a) 0
(b) 0.5
(c) 0.69
(d) 1

**Q53.** A node with labels {1,1,0,0,1,0} has p1 = ?
(a) 1/6
(b) 2/6
(c) 3/6
(d) 4/6

**Q54.** If a decision tree is at maximum depth 3, the deepest possible leaf is reached in how many hops from the root?
(a) 1
(b) 2
(c) 3
(d) 4

**Q55.** Radiological images require 10 bits per pixel, giving how many distinct grey levels?
(a) 256
(b) 512
(c) 1024
(d) 2048

---
---

# ANSWER KEY

## Bank A (Theoretical)

| Q  | Ans | Q  | Ans | Q  | Ans | Q  | Ans |
|----|-----|----|-----|----|-----|----|-----|
| 1  | b   | 10 | b   | 19 | b   | 28 | b   |
| 2  | b   | 11 | b   | 20 | b   | 29 | b   |
| 3  | c   | 12 | b   | 21 | d   | 30 | b   |
| 4  | c   | 13 | b   | 22 | b   | 31 | a   |
| 5  | c   | 14 | b   | 23 | b   | 32 | b   |
| 6  | b   | 15 | b   | 24 | c   | 33 | d   |
| 7  | d   | 16 | b   | 25 | b   | 34 | b   |
| 8  | c   | 17 | b   | 26 | b   | 35 | b   |
| 9  | a   | 18 | b   | 27 | c   |    |     |

## Bank B (Numerical)

| Q  | Ans | Q  | Ans | Q  | Ans | Q  | Ans |
|----|-----|----|-----|----|-----|----|-----|
| 36 | c   | 41 | c   | 46 | a   | 51 | c   |
| 37 | c   | 42 | b   | 47 | c   | 52 | a   |
| 38 | b   | 43 | b   | 48 | c   | 53 | c   |
| 39 | c   | 44 | d   | 49 | a   | 54 | c   |
| 40 | b   | 45 | d   | 50 | c   | 55 | c   |

---
---

# QUICK REVISION CHEAT SHEET (last-minute)

**Bayes rule:** P(C|X) = P(C)·P(X|C) / P(X). For classification, compare only P(C)·P(X|C).

**Naive Bayes:** P(C|x1..xn) ∝ P(C)·∏ P(xi|C).

**BBN joint:** P(x1..xn) = ∏ P(xj | Parents(xj)).

**Entropy (binary):** H(p) = -p log2 p - (1-p) log2(1-p). H(0.5)=1, H(0)=H(1)=0.

**Information gain:** IG = H(parent) - Σ (|child|/|parent|) H(child). Pick the feature with the largest IG.

**Variance reduction (regression):** ΔVar = Var(parent) - Σ (|child|/|parent|) Var(child).

**Eigen equation:** Ax = λx.

**PCA in 6 steps:** center -> covariance Σ=(1/m)X^T X -> eigenvectors/eigenvalues of Σ -> keep top k -> P is their matrix -> X̂ = XP.

**Variance explained by component j:** eigenvalue λj.

**PACS subsystems (5):** acquisition, PAC server, workstations (display/review), DBMS/storage (short/mid/long), communication network.

**HIS -> RIS -> PACS** integration is bidirectional; enter demographics once.

**Storage tiers:** Short term = SSD + RAID. Medium term = HDD. Long term = magnetic tape.

**Distributed PACS:** Mayo Clinic, fibre optic backbone, MR + CT + CR clusters + LTA.

**DDR:** Indirect (X-ray -> CsI -> aSi panel -> electronics). Direct (X-ray -> Selenium -> electronics).

**DICOM:** standard for storing, printing, transmitting medical images + metadata. Enables worklists and vendor interop.

**Medical image compression:** wavelets -> keep low-freq structure, drop high-freq noise. Same idea as hearing aids keeping 300 Hz - 6 kHz.

**Bit depth:** medical grayscale = 10 bits (1024 levels). Ordinary grayscale = 8 bits.

**CT intensity unit:** Hounsfield. Typical range -1000 (air) to +3000 (bone/metal). Water = 0 HU.

---

*Good luck. Read the chapters once thoroughly, then drill the MCQ banks twice, then just keep the cheat sheet open for the last hour.*
