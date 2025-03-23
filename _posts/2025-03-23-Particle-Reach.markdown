---
layout: splash
title: "Particle Reach"
date: 2025-03-23
categories: [Probability, Problems]
tags: [Random Walks, Probability]
math: true
---

## Problem Statement

Consider a particle that performs a random walk on the integers starting at position $$0$$. At each step, the particle moves from position $$i$$ to position $$i+1$$ with probability $$p$$, while the probability it moves from $$i$$ to $$i−1$$ is $$1−p$$. If $$p=\frac{1}{3}$$, find the probability the particle ever reaches position $$1$$

**Original Problem Link**: [Click here](https://www.quantguide.io/questions/particle-reach-i)

## Solution

It is obvious that counting cases is not feasible here. Clearly there are infinitely many cases, with no clear pattern leading to a solvable series summation. Instead, lets deal with conditional probabilities.

To recall, 

$$P(X) = \sum_{Y_i} P(X | Y_i) \times P(Y_i)$$

### Step 1: Basic Observations

There is a key observation here. I pose the following question
> "If the particle started at position -1, what will be the probability of it ever reaching 0? How about 1?"

Note that, the particle's probability of reaching 0 is the same as that of a particle's probability of reach 1 when it starts at 0. This is because this random walk does not depend on your current position, just relative distances.

Now, what about the second part? Say I denote the probability of particle reaching the position to its just right as $$p_1$$.
Note that in this case, the 

probability of particle reaching 2 steps to the right = P(Particle reaching 1 step right) * P(Particle reaching 1 step right)

How? Positional independence! As stated earlier, in this random walk, the probabilities are independent of your current position! This is essentially the product of 2 independent events, which are 
- Particle Reaching 1 step to the right
- Particle reaching another step to the right from this new position (making total distance 2)

Thus, $$p_2 = p_1^{2}$$

### Step 2: Equation Formation and Solution

Now, lets use the law of total probability to form an equation in $$p_1$$.

We know, 

$$P(X) = \sum_{Y_i} P(X | Y_i) \times P(Y_i)$$

Here, from the origin, 2 events are possible

- The particle moves one step right to 1, with probability $$p$$
- The particle moves one step left to -1, with probability $$1-p$$

Lets denote our event "particle reaching position 1" as $$X$$
Also, $$Y_i$$ would represent the particle moving either left or right.
Let $$Y_1$$ be particle moving left. This $$P(Y_1) = 1 - p$$. Similarly, let $$Y_2$$ be particle moving right. This $$P(Y_2) = p$$.

Also, from our discussion earlier, $$P(X \mid Y_1) = p_2 = p_1^{2}$$, and $$P(X \mid Y_2) = 1$$. Ofcourse, $$P(X) = p_1$$, and $$p = \frac{1}{3}$$, as given in the question.

Plugging the values and simplifying, we get the equation

$$2p_1^{2} - 3p_1 + 1 = 0$$

Solving, we get $$p_1 = 1, \frac{1}{2}$$

Clearly, $$p_1 != 1$$.


### Thus, the required probability is $$\frac{1}{2}$$

---

💡 Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section!
