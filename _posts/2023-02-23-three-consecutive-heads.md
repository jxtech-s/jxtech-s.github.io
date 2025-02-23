---
title: "Probability of Three Consecutive Heads"
categories:
  - Problems
tags:
  - Coin Flips
  - Consecutive Events
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
difficulty: Medium
---

What is the probability of getting three consecutive heads when flipping a fair coin 5 times?

## Solution

Let's solve this step by step:

1) First, let's understand what we're looking for:
   - We need sequences of 5 flips that contain HHH somewhere
   - The coin is fair, so P(H) = P(T) = $\frac{1}{2}$

2) The probability can be calculated using:

   $P(\text{3 consecutive heads}) = 1 - P(\text{no 3 consecutive heads})$

3) For a fair coin, each specific sequence has probability:

   $$P(\text{HHHHH}) = \left(\frac{1}{2}\right)^5 = \frac{1}{32}$$