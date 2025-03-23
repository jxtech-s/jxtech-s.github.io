---
layout: splash
title: "Graph Search I"
date: 2025-03-23
categories: [Expectations, Probability, Problems]
tags: [Expectations, Probability]
math: true
---

## Problem Statement

You are given an undirected graph with $$10$$ nodes. From every node, you are able to access any other node (including itself), all with an equal probability of $$\frac{1}{10}$$. What is the expected number of steps to reach all nodes at least once (rounded to the nearest step)?

**Original Problem Link**: [Click here](https://www.quantguide.io/questions/graph-search)

## Solution

It is clear that we must deal with conditional expectations in the given problem. As a recap, using conditional expectations, we get

$$E[X] = \sum_{Y_i} E[X \mid Y_i] P(Y_i)$$

### Step 1: Formulating Recursive Relation

Lets denote $$E_{i}$$ as the expected number of steps required to  visit $$i$$ un-visited nodes. Note that this does not count our current node.

Now, when the simulation starts, you will take 1 step and enter the first node. After this, 9 nodes remain to be visited. Now, when you take the next path, either you end up on the same node (with probability $$\frac{1}{10}$$) or you end up on a new node (with probability $$\frac{9}{10}$$). Note that, when you enter a new node, now the remaining expected number of steps will be $$E_{8}$$, as you have already visited 2 nodes.

Therefore, for our first iteration, we could write
$$E_{9} = (\frac{1}{10} \times (1 + E_{9})) + (\frac{9}{10} \times (1 + E_{8}))$$

Note that the + 1 is added in each term as you take one step to reach there.

### Step 2: Generalizing the Relation

After a few iterations, it will be clear that the relation can be generalized as follows - 
> "If you must visit n nodes more, then with probability $$\frac{10 - n}{10}$$ you will reach an already visited node (where you will take $$E_{n}$$ steps), and with probability $$\frac{n}{10}$$ you will visit a new node (where you will take $$E_{n-1}$$ steps)."

Therefore, 

$$E_{n} = (\frac{10 - n}{10} \times (1 + E_{n})) + (\frac{n}{10} \times (1 + E_{n-1}))$$

On simplification, we get

$$E_{n} = \frac{10}{n} + E_{n-1}$$

### Step 3: Solving Recursion

Now that we have established the recurrence relation 

$$E_{n} = \frac{10}{n} + E_{n-1},$$

we can solve it iteratively to find a general expression for $$E_{9}$$, which is the expected number of steps to visit 9 new nodes. Note that we will need to add one more step, which is to "start" the simulation, i.e. enter the graph in the first place, and visit our first node.

First, note that the recurrence starts with $$E_{0} = 0$$ since when no nodes are unvisited, no more steps are required.

Now, let’s compute the values step by step:

- For $$E_1$$:
  $$
  E_1 = \frac{10}{1} + E_0 = 10 + 0 = 10.
  $$

- For $$E_2$$:
  $$
  E_2 = \frac{10}{2} + E_1 = 5 + 10 = 15.
  $$

- For $$E_3$$:
  $$
  E_3 = \frac{10}{3} + E_2 = \frac{10}{3} + 15 \approx 3.33 + 15 = 18.33.
  $$

- For $$E_4$$:
  $$
  E_4 = \frac{10}{4} + E_3 = 2.5 + 18.33 \approx 20.83.
  $$

- For $$E_5$$:
  $$
  E_5 = \frac{10}{5} + E_4 = 2 + 20.83 \approx 22.83.
  $$

- For $$E_6$$:
  $$
  E_6 = \frac{10}{6} + E_5 = \frac{5}{3} + 22.83 \approx 1.67 + 22.83 = 24.5.
  $$

- For $$E_7$$:
  $$
  E_7 = \frac{10}{7} + E_6 = \frac{10}{7} + 24.5 \approx 1.43 + 24.5 = 25.93.
  $$

- For $$E_8$$:
  $$
  E_8 = \frac{10}{8} + E_7 = \frac{5}{4} + 25.93 \approx 1.25 + 25.93 = 27.18.
  $$

- For $$E_9$$:
  $$
  E_9 = \frac{10}{9} + E_8 = \frac{10}{9} + 27.18 \approx 1.11 + 27.18 = 28.29.
  $$

Finally, for our final answer, as discussed above, we have:

$$
  Ans = 1 + E_9 = 1 + 28.29 \approx 29.29
$$



### Thus, the expected number of steps to visit all 10 nodes at least once is approximately **29.29**, which rounds to **29** steps.



---

💡 Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section!
