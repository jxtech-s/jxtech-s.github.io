--- 
layout: splash 
title: "Modified RNG" 
date: 2025-03-29
categories: [Probability, Problems] 
tags: [Probability, Expectations, Conditional Expectation, Conditional Variance] 
math: true 
---  

## Problem Statement

Jimmy picks a number uniformly at random from (0,1). If Jimmy chooses x, then Jon picks a number from (x,1) uniformly at random. If Y represents the number Jon selects, in simplest form, find $$\frac{\mathbb{E}[Y]}{Var(Y)}$$

**Original Problem Link**: [Click here](https://www.quantguide.io/questions/modified-rng)

## Solution

### Step 1 - Compute Conditional Expectation $$\mathbb{E}[Y \mid X]$$ and Conditional Variance $$Var(Y \mid X)$$

For $$Y$$ uniform on $$(X,1)$$, the conditional expectation is:

$$\mathbb{E}[Y \mid X] = \frac{X+1}{2}$$

How? Its obvious that its gonna be the middle point! Alternatively, you can integrate and compute using the standard method.

Similarly, for Conditional Variance $$Var[Y \mid X]$$, we have

$$Var[Y \mid X] = \frac{(1-X)^2}{12}$$

### Step 2 - Total Expectation

Using the law of total expectation:

$$\mathbb{E}[Y] = \mathbb{E}[\mathbb{E}[Y \mid X]] = \mathbb{E}\left[\frac{X+1}{2}\right] = \int_0^1 \frac{x+1}{2} dx = \left[\frac{x^2}{4} + \frac{x}{2}\right]_0^1 = \frac{1}{4} + \frac{1}{2} = \frac{3}{4}$$

### Step 3 - Computing Total Variance

Using the law of total variance:

$$Var(Y) = \mathbb{E}[Var(Y \mid X)] + Var(\mathbb{E}[Y \mid X])$$

First, compute $$\mathbb{E}[Var(Y \mid X)]$$:

$$\mathbb{E}[Var(Y \mid X)] = \int_0^1 \frac{(1-x)^2}{12} dx$$

$$= \frac{1}{12} \int_0^1 (1-x)^2 dx = \frac{1}{12} \left[\frac{-1}{3}(1-x)^3\right]_0^1 = \frac{1}{12} \cdot \frac{1}{3} = \frac{1}{36}$$

Next, compute $$Var(\mathbb{E}[Y \mid X])$$:

$$Var(\mathbb{E}[Y \mid X]) = \mathbb{E}\left[\left(\frac{X+1}{2}\right)^2\right] - \left(\mathbb{E}\left[\frac{X+1}{2}\right]\right)^2$$

$$= \int_0^1 \frac{(x+1)^2}{4} dx - \left(\frac{3}{4}\right)^2 = \frac{1}{4} \int_0^1 (x^2 + 2x + 1) dx - \frac{9}{16}$$

$$= \frac{1}{4} \left[\frac{x^3}{3} + x^2 + x\right]_0^1 - \frac{9}{16} = \frac{1}{4} \left(\frac{1}{3} + 1 + 1\right) - \frac{9}{16} = \frac{1}{4} \cdot \frac{7}{3} - \frac{9}{16} = \frac{7}{12} - \frac{9}{16} = \frac{1}{48}$$

Therefore:

$$Var(Y) = \frac{1}{36} + \frac{1}{48} = \frac{7}{144}$$

### Final Answer

$$\frac{\mathbb{E}[Y]}{Var(Y)} = \frac{3/4}{7/144} = \frac{108}{7}$$

---

💡 Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section!
