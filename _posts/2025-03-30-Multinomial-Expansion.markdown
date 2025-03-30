---
layout: splash
title: "Multinomial Expansion"
date: 2025-03-30
categories: [Probability, Problems]
tags: [Combinatorics, Counting]
math: true
---

## Problem Statement

How many terms are there in the expansion of 

$$
(x_1 + x_2 + x_3 + x_4 + x_5 + x_6)^{18}
$$

after all like terms have been combined?

**Original Problem Link**: [Click here](https://www.quantguide.io/questions/multinomial-expansion)  

## Solution

### Step 1: Understanding the Expansion  

When expanding 

$$
(x_1 + x_2 + x_3 + x_4 + x_5 + x_6)^{18}
$$

each term in the expansion will be of the form:

$$
c \cdot x_1^{a_1} x_2^{a_2} x_3^{a_3} x_4^{a_4} x_5^{a_5} x_6^{a_6}
$$

where $$ a_1, a_2, a_3, a_4, a_5, a_6 $$ are non-negative integers that sum to 18:

$$
a_1 + a_2 + a_3 + a_4 + a_5 + a_6 = 18.
$$

Each unique term corresponds to a different way of assigning exponents to the six variables, regardless of order.  

### Step 2: Reduced Version - The Core Idea  

Instead of thinking in terms of exponents, simply answer:  
> "In how many ways can I divide 18 objects amongst 6 people, if each person can get 0 at min?"  

This is a direct application of the [Stars and Bars](https://en.wikipedia.org/wiki/Stars_and_bars_(combinatorics)) method, which states that the number of ways to distribute $$ n $$ identical objects among $$ k $$ groups is:

$$
\binom{n + k - 1}{k - 1}.
$$

Setting $$ n = 18 $$ (total power) and $$ k = 6 $$ (number of variables), we get:

$$
\binom{18 + 6 - 1}{6 - 1} = \binom{23}{5}.
$$

### Step 3: Compute the Binomial Coefficient  

Using the formula:

$$
\binom{23}{5} = \frac{23!}{5!(23 - 5)!} = \frac{23!}{5! \cdot 18!}.
$$

Computing step-by-step:

$$
\frac{23 \times 22 \times 21 \times 20 \times 19}{5 \times 4 \times 3 \times 2 \times 1}
$$

$$
= \frac{5173168}{120} = 33649.
$$


### Thus, the number of terms in the expansion is $$\mathbf{33649}$$

---

💡 Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section!
