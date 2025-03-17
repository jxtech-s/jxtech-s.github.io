---
layout: splash
title: "Confused Ant II"
date: 2025-03-17
categories: [Probability, Statistics, Problems]
tags: [Probability, Expectations]
math: true
---
## Problem Statement

An ant walks the corner of a 3D cube and moves to one of the three adjacent vertices with equal probability at each step. Find the expected number of steps needed for the ant to return to the vertex it started at.

**Original Problem Link**: [Click here](https://www.quantguide.io/questions/confused-ant-ii)

## Solution

Here from each corner, the ant can take any path with an equal probability of $$1/3$$.
We must realize that if we compute the probability of each possible path, and multiply it by the number of steps its taking, and take its summation over all possible cases, that would yes lead to our answer, but it is very tedious to compute.

A better alternative is to use the concept of Conditional Expectations.
It essentially states that

$$E[X] = \sum_{Y_i} E[X \mid Y_i] P(Y_i)$$

### Step 1: Identifying States

In the described problem, the ant can be uniquely at 4 possible positions.
1. At the starting point itself (call this $$A$$).
2. At a point only 1 edge away from $$A$$ (call this $$B$$).
3. At a point 2 edges away from $$A$$ (call this $$C$$).
4. At a point 3 edges away from $$A$$ (call this $$D$$. Note that there is only 1 such point, the one diagonally opposite to $$A$$).

This reduces our problem to a Markov Chain analysis, with transition probablities as follows - 

State $$A$$ to State $$B$$ = 1 
(How? -> Note that from $$A$$, you have 3 options to move, all symmetric and 1 edge away from $$A$$. This means you will definitely move to state $$B$$)

State $$B$$ to State $$A$$ = 1/3
(How? -> When you are at point $$B$$ (which is 1 edge away from $$A$$), you can move back to point $$A$$ with probability 1/3 (since at each point, all edges are equiprobable))

State $$B$$ to State $$C$$ = 2/3
(How? From State $$B$$, you either move back to $$A$$, or the other 2 edges lead to a point which is 2 edges away from $$A$$, this point $$C$$)

State $$C$$ to State $$B$$ = 2/3
(How? When at State $$C$$, 2 paths will lead to State $$B$$, and 1 will lead to $$D$$. Try to visualize this on a cube, with State $$C$$ being just adjacent to the opposite corner to $$A$$)

State $$C$$ to State $$D$$ = 1/3
(How? When at State $$C$$, 2 paths will lead to State $$B$$, and 1 will lead to $$D$$)

Thus, we can reduce the problem to 

> "Given the above State Transition Probabilities, find E[A], where A is the event of returning to point A after moving atleast once"

### Step 2: Forming the set of Expectation equations

For any State X, using the Conditional Expectation Equation described above

$$E[X] = \sum_{Y_i} E[X \mid Y_i] P(Y_i)$$

Where the states $$Y_i$$ represent points just adjacent to state $$X$$.

Solving for State A, we get

$$E[A] = 1 $$(for the 1 step we take) $$+3*1/3E[B]$$
Where $$E(B)$$ represents the expected value to reach state $$A$$ from $$B$$.

Simplifying, we get

$$E[A] = 1 + E[B]$$

Similarly, for State $$B$$, we have, 

Neighbouring States = A, C, C. Thus, 

$$E[B] = 1 +  1/3(E'[A]) + 2/3(E[C])$$

Note that here, $$E'[A]$$ is NOT $$E[A]$$.

$$E[A]$$ is the expected number of states to reach $$A$$ from $$A$$, given that we haven't moved before.

$$E'[A]$$ is the expected number of states to reach $$A$$ from $$A$$, given that we HAVE moved (since we went to $$B$$!). This is obviously 0, as you have already reached $$A$$!

Thus, we get

$$E[B] = 1 + 2/3 (E[C])$$

For states $$C$$ and $$D$$, following a similar analysis, we will get

$$E[C] = 1 + 1/3 (E[D]) + 2/3 (E[B])$$

(Note - for $$C$$, we are surrounded by 2 $$B$$'s and 1 $$D$$); and

$$E[D] = 1 + E[C]$$

(When at $$D$$, we are only surrounded by $$C$$'s. Just a reminder, $$D$$ is the opposite diagonal to $$A$$(our starting point), so this becomes trivial)

Therefore, we have a set of 4 equations and four variables ($$E[A]$$, $$E[B]$$, $$E[C]$$, $$E[D]$$)! These can be solved easily using backsubstitution.

### Step 3: Solving the Equations  

We have the following system of equations:

1. $$ E[A] = 1 + E[B] $$
2. $$ E[B] = 1 + \frac{2}{3} E[C] $$
3. $$ E[C] = 1 + \frac{1}{3} E[D] + \frac{2}{3} E[B] $$
4. $$ E[D] = 1 + E[C] $$

Now, 

From Equation (4):  

$$
E[D] = 1 + E[C]
$$

Substituting this into Equation (3):

$$
E[C] = 1 + \frac{1}{3} (1 + E[C]) + \frac{2}{3} E[B]
$$

Expanding:

$$
E[C] = 1 + \frac{1}{3} + \frac{1}{3}E[C] + \frac{2}{3}E[B]
$$

Rearrange:

$$
E[C] - \frac{1}{3} E[C] = \frac{4}{3} + \frac{2}{3}E[B]
$$

$$
\frac{2}{3}E[C] = \frac{4}{3} + \frac{2}{3}E[B]
$$

Multiplying both sides by $$ \frac{3}{2} $$:

$$
E[C] = 2 + E[B]
$$

From Equation (2):

$$
E[B] = 1 + \frac{2}{3} E[C]
$$

Substituting $$ E[C] = 2 + E[B] $$:

$$
E[B] = 1 + \frac{2}{3} (2 + E[B])
$$

$$
E[B] = 1 + \frac{4}{3} + \frac{2}{3}E[B]
$$

$$
E[B] - \frac{2}{3}E[B] = \frac{7}{3}
$$

$$
\frac{1}{3}E[B] = \frac{7}{3}
$$

$$
E[B] = 7
$$

Thus, finally we get, 

$$
E[A] = 1 + E[B] = 1 + 7 = 8
$$

### Therefore, the the expected number of moves required for the ant to reach back to its starting point is 8.

---

💡  Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section! 
