---
layout: splash
title: "Matching Die Trio"
date: 2025-03-24
categories: [Probability, Problems]
tags: [Combinatorics, Probability]
math: true
---

## Problem Statement

Three fair $$6$$−sided dice are rolled and their upfaces are recorded. Find the probability that the values showing upon rolling all three dice again is the same as the original three values recorded.

**Original Problem Link**: [Click here](https://www.quantguide.io/questions/matching-die-trio)

## Solution

We approach this problem using conditional expectation and casework probability. Since the three dice are not labeled, the probability of getting a matching set on the second roll depends on the structure of the first roll.

### Step 1: Classifying Cases Based on First Roll

When rolling three fair 6-sided dice, the possible cases based on distinctness of numbers are:

1. **Case 1: All three dice show distinct numbers.**  
   - The probability of this occurring:
     $$
     P(C_1) = \frac{\binom{6}{3} \cdot 3!}{6^3} = \frac{20 \cdot 6}{216} = \frac{120}{216}
     $$
   - On re-rolling, all 3 numbers must appear again. The number of favorable outcomes is the **number of ways to permute the same three numbers**, which is $$3!$$.  
     - Probability of matching:
       $$
       P(M \mid C_1) = \frac{3!}{6^3} = \frac{6}{216}
       $$

2. **Case 2: Two dice show the same number, and the third is different.**  
   - The probability of this occurring:
     $$
     P(C_2) = \frac{\binom{6}{1} \cdot \binom{5}{1} \cdot \frac{3!}{2!}}{6^3} = \frac{6 \cdot 5 \cdot 3}{216} = \frac{90}{216}
     $$
   - On re-rolling, we must obtain the same structure (two of one number and one of another), and the arrangement of dice does not matter.
     - Probability of matching:
       $$
       P(M \mid C_2) = \frac{\frac{3!}{2!}}{6^3} = \frac{3}{216}
       $$

3. **Case 3: All three dice show the same number.**  
   - The probability of this occurring:
     $$
     P(C_3) = \frac{6}{216}
     $$
   - On re-rolling, the only way to match is if the same number appears on all three dice.
     - Probability of matching:
       $$
       P(M \mid C_3) = \frac{1}{6^3} = \frac{1}{216}
       $$

### Step 2: Computing the Final Probability

Using the Law of Total Probability:

$$
P(M) = P(M \mid C_1) P(C_1) + P(M \mid C_2) P(C_2) + P(M \mid C_3) P(C_3)
$$

Substituting values:

$$
P(M) = \left(\frac{6}{216} \times \frac{120}{216}\right) + \left(\frac{3}{216} \times \frac{90}{216}\right) + \left(\frac{1}{216} \times \frac{6}{216}\right)
$$

$$
P(M) = \frac{720}{46656} + \frac{270}{46656} + \frac{6}{46656}
$$

$$
P(M) = \frac{996}{46656}
$$

$$
P(M) = \frac{83}{3888}
$$


### Thus, the probability that the second roll matches the first roll is $$\frac{83}{3888}$$

---

💡 Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section!
