---
layout: splash
title: "Breaking Stick"
date: 2025-02-23
categories: [Probability, Statistics, Problems]
tags: [Probability, Uniform Distribution, Triangle, Integration]
math: true
---

### Problem Statement  
A stick of length L drops and breaks at a random point distributed uniformly across the length.  
What is the expected length of the smaller part?  

---

### Solution  

As given in the question, the point where the stick will break is uniformly random.  

Now, lets consider, what is the probability, that a particular element (very small) point will be chosen (which is at a distance $$ x $$ from one end)?  

Very small, right? Yes!  

We must quantify this using calculus.  

We can say that the probability will be:

$$
\frac{dx}{L}
$$

where $$ L $$ is the length of the rod.  

Now, if this is the case, then the rod will break into 2 parts, one with length $$ x $$, other with $$ L-x $$.  

Using the fundamental definition of Expectation, we can say that  

$$
E[l] = \sum (l.P(l)), \quad l \text{ varies from } 0 \text{ to } \frac{L}{2}
$$

(as we are looking at the smaller edge)  

Here, $$ P(l) $$ is:

$$
\frac{dl}{L}, \quad \text{right? No!}
$$

$$ P(l) $$ means what's the probability that the smaller part will have a length $$ l $$.  

Note that there are 2 points where a rod can break, for the smaller length to be a particular $$ l $$  
(One is at $$ l $$ distance from one end, the other is at $$ l $$ distance from the other end).  

Thus,  

$$
P(l) = \frac{2 \, dl}{L}
$$

Now, the sigma becomes an integration as we have elemental quantities involved.  

Evaluating the integral, we get  

$$
E[l] = \int_0^{L/2} l \cdot \frac{2 \, dl}{L}
$$

$$
= \frac{2}{L} \int_0^{L/2} l \, dl
$$

$$
= \frac{2}{L} \times \left[ \frac{l^2}{2} \right]_0^{L/2}
$$

$$
= \frac{2}{L} \times \frac{(L/2)^2}{2}
$$

$$
= \frac{2}{L} \times \frac{L^2}{8}
$$

$$
= \frac{L}{4}
$$

### Final Answer

Thus, the expected length of the smaller part is:

$$
\boxed{\frac{L}{4}}
$$


---

💡  Did you enjoy this problem? Check out more puzzles in the Problems section! 
