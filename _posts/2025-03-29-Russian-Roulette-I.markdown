---
layout: splash
title: "Russian Roulette I"
date: 2025-03-29
categories: [Probability, Problems]
tags: [Probability]
math: true
---

## Problem Statement

You're playing a game of Russian Roulette with a friend. The six-chambered revolver is loaded with one bullet. Initially, the cylinder is spun to randomize the order of the chambers. The two of you take turns pulling the trigger until the person who fires the gun loses. Given that the cylinder is not re-spun after each turn, what is the probability that you win if your friend goes first?

**Original Problem Link**: [Click here](https://www.quantguide.io/questions/russian-roulette-i)

## Solution

### Step 1: Understanding the Setup

The revolver has 6 chambers, and exactly one of them contains a bullet. Since the cylinder is spun at the start, the bullet is equally likely to be in any of the 6 positions.

The game proceeds in turns:
- Your friend goes first.
- If the bullet is in the chamber they fire, they lose immediately.
- Otherwise, the turn passes to you.
- The game continues until someone loses.

### Step 2: Analyzing Possible Bullet Positions

Let's label the chambers $$1$$ to $$6$$, where $$1$$ is the chamber fired first, $$2$$ is fired second, and so on.

- If the bullet is in chamber $$1$$, your friend loses immediately.
- If the bullet is in chamber $$2$$, you lose immediately.
- If the bullet is in chamber $$3$$, your friend fires an empty chamber, then you fire an empty chamber, then your friend fires chamber $$3$$ and loses.
- If the bullet is in chamber $$4$$, you lose (similar reasoning).
- If the bullet is in chamber $$5$$, your friend loses.
- If the bullet is in chamber $$6$$, you lose.

Thus, we win if the bullet is in chambers $$1$$, $$3$$ or $$5$$.

### Step 3: Computing the Probability

Since each chamber is equally likely to contain the bullet, the probability of each case is:

$$
\mathbb{P}(\text{Bullet in chamber } i) = \frac{1}{6}
$$

From our analysis, we win in 3 out of the 6 cases (chambers $$1$$, $$3$$ and $$5$$).

Thus, the probability of winning is:

$$
\frac{3}{6} = \frac{1}{2}
$$

### Thus, the probability that we will win is $$\frac{1}{2}$$

---

💡 Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section!
