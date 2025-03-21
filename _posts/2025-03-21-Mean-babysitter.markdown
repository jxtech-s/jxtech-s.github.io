---
layout: splash
title: "Mean babysitter"
date: 2025-03-21
categories: [Combinatorics, Statistics, Problems]
tags: [Combinatorics, Counting]
math: true
---
## Problem Statement

10 kids are really hungry! Their babysitter has 12 units of food to give. However, she decides she only wants to give 4 of the children food. How many ways can she distribute the food units such that 6 of the children are hungry (receive no food), and the other 4 children receive at least 1 unit of food each?

**Original Problem Link**: [Click here](https://www.quantguide.io/questions/mean-babysitter)

## Solution

### Step 1: Understanding the Required Tasks

To distribute the food, we need to:

1. Choose 4 children who will receive food (equivalently, choose 6 children who won’t).
2. Distribute 12 units of food among these 4 children, ensuring that each child gets at least 1 unit.

### Step 2: Calculating the Number of Ways

#### **Step 1: Choosing 4 Children**
Since we need to select 4 children out of 10, the number of ways to do this is:

$$
\binom{10}{4} = \binom{10}{6} = 210
$$

(since choosing 4 to receive food is the same as choosing 6 to not receive food).

#### **Step 2: Distributing the Food**
Let the food received by the four chosen children be represented as:

$$
f_{a} + f_{b} + f_{c} + f_{d} = 12
$$

where $$ f_{a}, f_{b}, f_{c}, f_{d} $$ represent the food units received by each of the 4 children.

Since each child must get at least 1 unit, we make the substitution:

$$
f_{a} = 1 + x_{a}, \quad f_{b} = 1 + x_{b}, \quad f_{c} = 1 + x_{c}, \quad f_{d} = 1 + x_{d}
$$

Rewriting the equation:

$$
(1 + x_{a}) + (1 + x_{b}) + (1 + x_{c}) + (1 + x_{d}) = 12
$$

which simplifies to:

$$
x_{a} + x_{b} + x_{c} + x_{d} = 8
$$

This is now a classic "stars and bars" problem, where we distribute 8 extra food units among 4 children. The number of ways to do this is:

$$
\binom{8 + 4 - 1}{4 - 1} = \binom{11}{3} = 165
$$

### Step 3: Computing the Final Answer

The total number of valid distributions is:

$$
\binom{10}{4} \times \binom{11}{3} = 210 \times 165 = 34,650
$$

Thus, the final answer is:

$$
\mathbf{34,650}
$$

---

💡 Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section!  
