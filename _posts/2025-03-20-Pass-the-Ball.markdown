---
layout: splash
title: "Pass the ball"
date: 2025-03-18
categories: [Probability, Statistics, Problems]
tags: [Probability, Conditional Probability]
math: true
---
## Problem Statement

You and 4 other people are sitting in a circle. You are given a ball to start the game. Every second of this game, the person with the ball has three choices they can make. They can either pass the ball to the left, pass the ball to the right, or keep the ball (all with equal probability). This game goes on till someone keeps the ball. What is the probability that you are the person to end the game and keep the ball?

**Original Problem Link**: [Click here](https://www.quantguide.io/questions/pass-the-ball)

## Solution

Lets call the people $$A$$(me), $$B$$, $$C$$, $$D$$, $$E$$.
Note that $$B$$ and $$E$$ are symmetric (at distance 1)
Similarly, $$C$$ and $$D$$ are symmetric (at distance 2)

If one thinks through the question trivially, a simple approach could be to just "count" all possible ways the game ends at person A. But soon one realises there are inifinitely many ways, although possibly countable, but not-so-trivial after all!

A simpler approach involves identifying markov states and using conditional probabilities. The fundamental law of total probability states

$$P(X) = \sum_{Y_i} P(X | Y_i) \times P(Y_i)$$

### Step 1: Identifying States

We can define 5 simple states, $$S_{A}$$, $$S_{B}$$, $$S_{C}$$, $$S_{D}$$, $$S_{E}$$, with state $$S_{i}$$ representing that the ball is with the $$i_{th}$$ person.

Now, consider the probability that the ball is with person $$i$$, and the game ends with person $$A$$. Lets denote this as $$P(A* \mid i)$$, where $$A*$$ means that the game will end with person $$A$$.

At each state, the person can either stop the game, or pass it on to its neighbours with equal probabilities! Lets try to form a set of equations in $$P(A* \mid i)$$ using this.

### Step 2: Forming the set of Probability equations

For each state $$S_{i}$$, lets represent $$P(A* \mid i)$$ in terms of its neighbours.

Now,

For state $$S_{A}$$ (i.e. the person $$A$$ has the ball itself), I can either 
- Stop the game, with prob $$\frac{1}{3}$$
- Pass the ball to player $$B$$, with prob $$\frac{1}{3}$$, thus moving to state $$S_{B}$$
- Pass the ball to player $$E$$, with prob $$\frac{1}{3}$$, thus moving to state $$S_{E}$$

Therefore, we can write

$$P(A* \mid A) = \frac{1}{3} + P(A* \mid B)\frac{1}{3} + P(A* \mid E)\frac{1}{3}$$

Note that here the first term represents $$A$$ ending the game there itself.

Similarly, for state $$S_{B}$$

$$P(A* \mid B) = P(A* \mid A)\frac{1}{3} + P(A* \mid C)\frac{1}{3}$$

and for state $$S_{C}$$

$$P(A* \mid C) = P(A* \mid B)\frac{1}{3} + P(A* \mid D)\frac{1}{3}$$

> For more intuition on how these equations are formed, think of it like "the probability that A ends the game, given that the ball is currently with C, is that either he passes the ball to B(first neighbour) and we compute this same probability for B, or that he passes on the ball to D(other neighbour), and we compute the same for D. Its somewhat "recursive". For A, another possiblility (that I end the game right now) is added, leading to an extra $$\frac{1}{3}$$

Now, lets utilize some symmetry!

Clearly, 
$$P(A* \mid C) = P(A* \mid D)$$
and $$P(A* \mid B) = P(A* \mid E)$$

(As C and D are symmetrically placed around A; same with B and E)

Thus, we can reduce the equations to 3 unique variables, $$P(A* \mid A)$$, $$P(A* \mid B)$$ and $$P(A* \mid C)$$

### Step 3: Solving the equations

Now, substituting:

$$
a = P(A* \mid A)
$$

$$
b = P(A* \mid B) = P(A* \mid E)
$$

$$
a = P(A* \mid C) = P(A* \mid D)
$$

We get, 

$$
a = \frac{1}{3} + \frac{2b}{3}
$$

$$
b = \frac{a + c}{3}
$$

$$
c = \frac{b + c}{3}
$$

Solving these, we get:

$$
a = \frac{5}{11}
$$

### Therefore, the probability that we(Person $$A$$) will end the game is $$\frac{5}{11}$$

---

💡  Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section! 
