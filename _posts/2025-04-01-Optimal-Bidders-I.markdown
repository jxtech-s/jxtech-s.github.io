---
layout: splash
title: "Optimal Bidders I"
date: 2025-04-01
categories: [Probability, Problems]
tags: [Probability, Statistics, Expectations]
math: true
---

## Problem Statement

Carter has come into contact with a bounty of gold. He takes it to an auction shop. The shop tells him that every bidder will place a bid uniformly between $500 and $1000. They also say they can recruit bidders for $5 per person.

Carter needs to figure out the optimal number of bidders to maximize his expected payout. What is this maximum payout?

**Original Problem Link**: [Click here](https://www.quantguide.io/questions/optimal-bidders-i)  

## Solution

### Step 1: Modeling the Maximum Bid  

Each bidder bids randomly between 500 and 1000. Now, if there are $$ n $$ bidders, we can assume that the bids will be evenly spaced between 500 and 1000 on average.  

The expected spacing between bids is:

$$
\frac{500}{n+1}
$$

Thus, the expected maximum bid will be:

$$
M(n) = 1000 - \frac{500}{n+1}
$$

### Step 2: Writing the Expected Payout  

Now, Carter’s expected earnings are simply:

$$
\text{Max bid} - \text{Cost of bidders}
$$

Which gives us:

$$
E(n) = M(n) - 5n
$$

Substituting $$ M(n) $$:

$$
E(n) = 1000 - \frac{500}{n+1} - 5n
$$

Now, we need to maximize this function.

### Step 3: Finding the Optimal $$ n $$  

We differentiate $$ E(n) $$ and set it to 0:

$$
\frac{d}{dn} \left( 1000 - \frac{500}{n+1} - 5n \right) = 0
$$

$$
\frac{500}{(n+1)^2} = 5
$$

Solving:

$$
500 = 5(n+1)^2
$$

$$
100 = (n+1)^2
$$

$$
n+1 = 10 \Rightarrow n = 9
$$

Thus, the optimal number of bidders is $$ n = 9 $$.

### Step 4: Calculating the Maximum Expected Payout  

Substituting $$ n = 9 $$:

$$
E(9) = 1000 - \frac{500}{10} - 5(9)
$$

$$
= 1000 - 50 - 45
$$

$$
= 905
$$

### Thus, the maximum expected payout Carter can get is $905.

---

💡 Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section!
