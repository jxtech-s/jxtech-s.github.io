---
layout: splash
title: "Intersecting Chords"
date: 2025-02-26
categories: [Probability, Statistics, Problems]
tags: [Probability, Combinatorics, Counting Principle]
math: true
---

## Problem Statement  

10 chords with uniformly randomly chosen endpoints are drawn on a circle. What is the expected number of intersections?  

**Original Problem Link:** [Click here](https://www.quantguide.io/questions/intersecting-chords)  

---  

## Solution  

Let us consider the simpler case of 2 chords intersecting. Once we have that, perhaps we can use it to formulate something for 10 chords.  

Now, focusing on the subproblem:  
> I draw 2 chords in a circle at random, what is the probability that they intersect? Equivalently, what is the expected number of intersections?  

To solve this, there exist two fundamental approaches.  

### Approach 1 - [Complicated stuff alert]  

One is a rigorous mathematical treatment, which involves considering that a random chord drawn in a circle will be defined by 2 angles (say $$ \theta_1 $$ and $$ \theta_2 $$), where these angles define the start and the endpoint of the chord with respect to a given reference radius. Both these angles will have a uniform $$ (0, 2\pi) $$ distribution.  

Thus, the angle made by the chord towards the circumference will be $$ (\theta_1 - \theta_2) $$, which will have a triangular distribution. Once this is computed, we must calculate:  

$$
2 \times \frac{\theta}{2\pi} \times \left( 1 - \frac{\theta}{2\pi} \right)
$$  

and integrate over all $$ \theta $$ to compute the required probability.  

How did this expression come?  
Given a chord, to make another intersecting chord, I can choose any random point from one "side" of the chord, and another from the other "side."  

Note that the probability of choosing a point from one "side" is $$ \frac{\theta}{2\pi} $$, where $$ \theta $$ is the angle from the center subtended by the chord in that side. Also, the "2" in the start is added because the ordering of points is unique. (As in, either I choose one end from side A, other from side B, or one end from side B, and other from side A) (Here side A and B mean different sides of the chord (one is subtending angle $$\theta$$, other is subtending $$2\pi - \theta$$))

Clearly, this approach is a bit brain-racking (but it works; I have manually calculated and verified the answer. If interested, feel free to hit me up, and we can discuss this further!).  

### A Simpler Approach  

Clearly, 2 chords drawn randomly are essentially defined by 4 points chosen at random on a circle. Say $$ A, B, C, D $$.  

Now, let's think of how we can connect these points such that the chords intersect. To connect them, these 3 arrangements are possible:  

1. $$ A $$-$$ B $$, $$ C $$-$$ D $$  
2. $$ A $$-$$ C $$, $$ B $$-$$ D $$  
3. $$ A $$-$$ D $$, $$ B $$-$$ C $$  

Note that out of the 3, only arrangement (2) will result in an intersection. Since everything here is uniformly random, all arrangements are equally likely, hence the probability of intersection is $$ \frac{1}{3} $$.  

Thus, we have now fairly established that the probability of intersection of 2 chords drawn at random in a circle is $$ \frac{1}{3} $$. (Read up the above explanation again, it may take time to digest).  

---  

### Moving on to the original problem. What if we have 10 chords?  

It's actually fairly simple. From the 10 chords, select any 2 at random. What is the probability they will intersect? $$ \frac{1}{3} $$, right? (As we computed above).  

This means every pair will essentially contribute $$ \frac{1}{3} $$ to the expected number of intersections. (Note that the probability of overlapping intersections, i.e., more than 2 chords intersecting at the same point, is VERY small).  

Now, in how many ways can we select 2 chords at random from 10?  

$$
\binom{10}{2} = \frac{10 \times 9}{2}
$$  

Thus, the expected number of intersections in the case of 10 chords will be:  

$$
\binom{10}{2} \times \frac{1}{3} = \frac{10 \times 9}{2 \times 3} = 15.
$$  

---  

### Therefore, the answer is **15** intersections.  

*(PS: On the website linked above, it shows incorrect for "15." One must enter "45/3" instead. A weird error, tbh. Possibly because 10C2 is 45, and p(for 2 chords) = 1/3, Thus 45/3)*  

---

💡  Did you enjoy this problem? Check out more puzzles in the Problems section! 
