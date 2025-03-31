---
layout: splash
title: "Comparing Flips II"
date: 2025-03-31
categories: [Probability, Problems]
tags: [Probability, Conditional Probability]
math: true
---

## Problem Statement

You and your friend are playing a game with a fair coin, tossing it and writing down the outcomes. You win if HTH appears before HHT, else your friend wins. What is the probability that your friend wins?

**Original Problem Link**: [Click here](https://www.quantguide.io/questions/comparing-flips-ii)  

## Solution

### Step 1: Understanding the Game  

The game continues until either HTH or HHT appears first. To analyze this, we consider the probability of winning from the instance the first H appears.

Let $$ p $$ be the probability that I win from this point onward. We now determine $$ p $$ using conditional probability.

### Step 2: Breaking Down Possible Sequences  

After the first H, the next flip can be:

1. H → Sequence: HH_  
2. T → Sequence: HT_

We analyze both cases separately.

#### Case 1: The sequence becomes HH_  

- The next flip can be H (forming HHH_) or T (forming HHT).
- If we get HHT, my friend immediately wins.
- If we get HHH, the sequence will continue indefinitely, but since the only way to eventually break out is forming HHT, I am guaranteed to lose.
- Thus, if HH occurs, I cannot win.  
  $$
  P(\text{Winning} \mid HH) = 0
  $$

#### Case 2: The sequence becomes HT_  

- If the next flip is H, then HTH forms, and I immediately win.
- If the next flip is T, then the sequence extends to HTT_ and continues.
- Now, at some point in the future, an H must eventually appear (since an infinite T sequence has probability 0).
- When this H appears, the game resets to the same original scenario, meaning my probability of winning from here is still $$ p $$.

Thus,  

$$
P(\text{Winning} \mid HTT) = p.
$$

and

$$
P(\text{Winning} \mid HTH) = 1.
$$

Now, consider that I said earlier "consider the case from the first H". Since the game is an inifinte sequence, a series of TTTTT... is not possible, hence the first H is guarateed to appear. Therefore, I can argue that this probability $$p$$ is the same as me winning in any case from the start of the game, and not just from the first H.

### Step 3: Setting Up the Probability Equation  

Obviously, 

$$P(HTT) = P(HTH) = \frac{1}{4}$$

and

$$P(HH) = \frac{1}{2}$$

Using the law of total probability, we can write


$$
p = \frac{1}{4} (1) + \frac{1}{4} (p) + \frac{1}{2} (0)
$$

$$
p = \frac{1}{4} + \frac{1}{4} p
$$

$$
\frac{3}{4} p = \frac{1}{4}
$$

$$
p = \frac{1}{3}
$$

Thus, the probability that I win is $$ \frac{1}{3} $$, and the probability that my friend wins is:

$$
1 - \frac{1}{3} = \frac{2}{3}.
$$

### Thus the probability my friend wins is $$\mathbf{\frac{2}{3}}$$

---

💡 Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section!
