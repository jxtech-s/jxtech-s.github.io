---
layout: splash
title: "Random Ratio"
date: 2025-02-26
categories: [Probability, Statistics, Problems]
tags: [Probability, Integration]
math: true
---
## Problem Statement

$$p$$ and $$q$$ are two points chosen at random between 0 $$\&$$ 1. What is the probability that the ratio $$p/q$$ lies between 1 $$\&$$ 2?

**Original Problem Link**: [Click here](https://brainstellar.com/puzzles/medium/112)

## Solution

We have 2 random variables (RVs) $$p \& q$$ here. Let's try to fix one for simplicity, and then use that result to develop a general solution where both are RVs.

### Step 1: Fixing q

Say we fix $$q$$ at some value between 0 and 1. Now, the given problem reduces to:

> "q is a fixed value between 0 and 1. p ~ Uniform(0,1). What is the probability that 1 < p/q < 2?"

This question is fairly straightforward.

### Step 2: Rearranging the Inequality

Let's rearrange the inequality:

$$
1 < \frac{p}{q} < 2
$$

$$
q < p < 2q
$$

Also, note that since p is restricted in (0,1), we must say:

$$
\max(0,q) < p < \min(2q, 1)
$$

But since q is also restricted in (0,1), we have $$
\max(0,q) = q
$$

Thus, the final expression is:

$$
q < p < \min(2q,1)
$$

### Step 3: Computing the Probability

Now, let's compute the probability that p will lie within this range.

As $$
p \sim \text{Uniform}(0,1)
$$, the required probability:

$$
P = \frac{\min(1,2q) - q}{1} = \min(2q,1) - q
$$

(Note: The probability is simply the length of the required range divided by the length of the total range. This is also visible by intuition)

### Step 4: Considering q as a Random Variable

Now, note that this is the case when q is fixed. But q itself will vary from 0 to 1.

We can write the above probability as "conditioned on" a particular q:

$$
P(E|q) = \min(2q,1) - q
$$

(Where E is our required event of $$
1 < \frac{p}{q} < 2
$$)

### Step 5: Using the Law of Total Probability

Using fundamental laws, we have:

$$
P(E) = \sum P(E|q)P(q)
$$

What is P(q)? Essentially the probability of choosing a particular value from 0 to 1, an infinite set! Clearly very small! Let's use calculus to denote this. 

$$
P(q) = \frac{dq}{1} = dq
$$

Thus,

$$
P(E) = \int_0^1 (\min(2q,1) - q) \, dq
$$

### Step 6: Solving the Integral

To solve this integral, we need to split it into two parts:

1. From 0 to 1/2, where $$ \min(2q,1) = 2q $$
2. From 1/2 to 1, where $$ \min(2q,1) = 1 $$

Now, 


$$P(E) = \int_0^{1/2} (2q - q) \, dq + \int_{1/2}^1 (1 - q) \,$$

$$ = \int_0^{1/2} q \, dq + \int_{1/2}^1 (1 - q) \, dq $$

$$ = [\frac{q^2}{2}]_0^{1/2} + [q - \frac{q^2}{2}]_{1/2}^1 $$

$$ = (\frac{1}{8} - 0) + ((1 - \frac{1}{2}) - (\frac{1}{2} - \frac{1}{8})) $$

$$ = \frac{1}{8} + \frac{1}{2} - \frac{3}{8} = \frac{1}{4} $$





### Therefore, the probability that the ratio $$p/q$$ lies between 1 and 2 is $$\frac{1}{4} $$ or $$0.25$$ or $$25\%$$.

---

PS - A similar integration is involved in the problem [Random-Angle-II](https://jxtech-s.github.io/probability/statistics/problems/2025/02/23/Random-Angle-II.html). Check it out for a more detailed explaination incase of any confusions!.

---

💡  Did you enjoy this problem? Check out more puzzles in the Problems section! 
