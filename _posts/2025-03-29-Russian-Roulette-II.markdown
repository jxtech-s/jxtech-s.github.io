---
layout: splash
title: "Russian Roulette II"
date: 2025-03-29
categories: [Probability, Problems]
tags: [Probability, Series]
math: true
---

## Problem Statement

You're playing a game of Russian Roulette with a friend. The six-chambered revolver is loaded with one bullet. Initially, the cylinder is spun to randomize the order of the chambers. The two of you take turns pulling the trigger until the person who fires the gun loses. Given that the cylinder is re-spun after each turn, what is the probability that you win if your friend goes first?

**Original Problem Link**: [Click here](https://www.quantguide.io/questions/russian-roulette-ii)  
**First version**: [Russian Roulette I](https://jxtech-s.github.io/probability/problems/2025/03/29/Russian-Roulette-I.html)

---

## Solution

### Step 1: Understanding the Difference

Unlike the previous version, the key difference here is that after each turn, the cylinder is re-spun. This means:
- Every turn is independent of the previous turns.
- At every turn, the probability of firing the bullet remains constant.

Since the chamber is re-randomized, on each turn, the probability that the player firing will shoot the chamber with the bullet is:

$$
\frac{1}{6}
$$

Similarly, the probability that the bullet is not fired on any given turn is:

$$
\frac{5}{6}
$$

### Step 2: Analyzing the Winning Chances

For you to win, the game must end on an odd-numbered turn (i.e., your friend fires and survives, then you fire and lose).

- Case 1: Your friend loses immediately (turn 1).  
  - Probability = $$\frac{1}{6}$$.
  
- Case 2: Your friend survives, you survive, then your friend loses (turn 3).  
  - Probability = $$\left(\frac{5}{6}\right) \times \left(\frac{5}{6}\right) \times \frac{1}{6}$$.

- Case 3: Your friend survives, you survive, your friend survives, you survive, then your friend loses (turn 5).  
  - Probability = $$\left(\frac{5}{6}\right)^2 \times \left(\frac{5}{6}\right)^2 \times \frac{1}{6}$$.

Generalizing, the probability that your friend loses on the 2(k-1)th turn is (factor of 2 as we will win only in the odd numbered cases) -

$$
\left(\frac{5}{6}\right)^{2(k-1)} \times \frac{1}{6}
$$

Summing this up for all $$ k $$:

$$
P(\text{You win}) = \sum_{k=1}^{\infty} \left(\frac{5}{6}\right)^{2(k-1)} \times \frac{1}{6}
$$

### Step 3: Summing the Infinite Geometric Series

This is a geometric series with first term:

$$
a = \frac{1}{6}
$$

and common ratio:

$$
r = \left(\frac{5}{6}\right)^2 = \frac{25}{36}
$$

Using the sum formula for an infinite geometric series:

$$
S = \frac{a}{1 - r}
$$

we get:

$$
P(\text{You win}) = \frac{\frac{1}{6}}{1 - \frac{25}{36}}
$$

$$
= \frac{\frac{1}{6}}{\frac{11}{36}}
$$

$$
= \frac{1}{6} \times \frac{36}{11} = \frac{6}{11}
$$

### Thus, the probability that we will win is $$\frac{6}{11}$$

---

💡 Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section!
