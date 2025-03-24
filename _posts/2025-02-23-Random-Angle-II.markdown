---
layout: splash
title: "Random Angle II"
date: 2025-02-23
categories: [Probability, Statistics, Problems]
tags: [Probability, Uniform Distribution, Triangle, Integration]
math: true
---

##  Problem Statement  

A right triangle is being formed with legs labeled  $$A$$  and  $$B$$. The random lengths of legs  
 $$A$$  and  $$B$$  are both IID  Uniform(0,1)  random variables.  

Let  $$\theta$$  be the angle (in radians) opposite to side  $$A$$. Find the probability that:  

$$  P(\theta > \pi/3)$$  

 Original Problem Link:  [Click here](https://www.quantguide.io/questions/random-angle-ii)  

---

##  Solution   
Now we must find $$ P(\theta > \pi/3)$$.  

Note that,  

$$ \tan(\theta) = \frac{A}{B}$$  

where  $$A$$  and  $$B$$  both are IID  Uniform(0,1)  random variables.  

For convenience, let's fix  $$B$$  for now. Then, this problem becomes much simpler. It reduces to:  

   
>  Given  $$  \tan(\theta) = \frac{A}{B}$$, where  $$A$$  is  Uniform(0,1) ,$$B$$  is a given constant,  
find $$  P(\theta > \pi/3)$$. 

Let's try and solve this sub-problem:  

$$  P(\theta > \pi/3) = P(\tan(\theta) > \sqrt{3}) = P(\frac{A}{B} > \sqrt{3}) = P(A > B\sqrt{3})$$  

Now, since  $$A$$  is a  Uniform(0,1)  random variable, clearly:  

$$  P(A > x) = \max(0, 1-x)$$  

 (How? 🤔)   
- If $$  x$$ is between  0  and  1 , well and good.  
- If $$  x > 1$$, since  A  cannot be greater than 1, $$  P(A > x) = 0$$.  
- Still confused? Try intuitively finding $$  P(A>0)$$, $$  P(A>1/2)$$, and $$  P(A>1)$$. You will see the essence of the above expression.
- Still confused? Read up on  PDF (Probability Density Function)  and  CDF (Cumulative Density Function)   
  of the  continuous Uniform distribution .  

Therefore, for the smaller sub-problem above:  

$$  P(A > B\sqrt{3}) = 1 - B\sqrt{3}$$  

for all  $$  1 - B\sqrt{3} \geq 0 \Rightarrow B \leq 1/\sqrt{3}$$ .  

Essentially, this is equivalent to writing:  

$$  P(\theta > \pi/3 \mid B) = 1 - B\sqrt{3}$$  

 (Why? 🤔)   
Because  $$  P(\theta > \pi/3 \mid B)$$  represents the probability of $$  \theta$$ being greater than $$  \pi/3$$,  
 given some B / conditioned on some B .  

This is exactly what we calculated above! By fixing  $$B$$ , we found  $$  P(\theta > \pi/3)$$   
in terms of some  $$B$$ , for a given  $$B$$.  

But of course, as the question states, $$B$$ is also a  Uniform(0,1)  random variable.  

We shall now use the  fundamental law of total probability  here.  

---

###  Step 2: Using the Law of Total Probability   
Note that we can say:  

$$  P(\theta > \pi/3) = \sum P(\theta > \pi/3 \mid B) P(B)$$  

for all  $$B$$.  

Now, we must compute  $$  P(B)$$ .  

What exactly does this represent? 🤔  

It basically asks:  

> What is the probability of choosing a particular $$B$$ from $$[0,1]$$?

Very small, right?  

How do we quantify this?  Using calculus!   

We can say that the probability of choosing a particular $$  B$$ from $$  [0,1]$$ is essentially:  

$$  \frac{dB}{1} = dB$$  

where  $$dB$$  is a very small term.  

Notice that now our summation actually  reduces to a simple integration , due to our usage of  
 "elemental B" or "$$dB$$"  to model $$  P(B)$$.  

Ideally, we should vary  $$B$$  from  $$0$$ to $$1$$, but note that  $$B$$ must be ≤ $$\frac{1}{\sqrt 3}$$ ,  
otherwise  $$  P(\theta > \pi/3 \mid B) = 0$$ .  

Therefore, we rewrite the above expression as a definite integral:  

$$  P(\theta > \pi/3) = \int_{0}^{1/\sqrt{3}} (1 - B\sqrt{3}) dB$$  

---

###  Step 3: Solving the Integral   
Expanding the integral:  

$$  \int_{0}^{1/\sqrt{3}} (1 - B\sqrt{3}) dB$$  

We solve separately:  

$$  \int 1 \, dB = B$$  

$$  \int B\sqrt{3} \, dB = \frac{\sqrt{3} B^2}{2}$$  

Evaluating from  $$0$$  to  $$1/√3$$:  

$$  P(\theta > \pi/3) = \left[ B - \frac{\sqrt{3} B^2}{2} \right]_{0}^{1/\sqrt{3}}$$  

Substituting  $$B = 1/√3$$:  

$$  P(\theta > \pi/3) = \frac{1}{\sqrt{3}} - \frac{\sqrt{3} (1/3)}{2}$$  

$$  = \frac{1}{\sqrt{3}} - \frac{\sqrt{3}}{6}$$  

$$  = \frac{2}{2\sqrt{3}} - \frac{1}{2\sqrt{3}}$$  

$$  = \frac{1}{2\sqrt{3}}$$  

Thus,  

$$  \boxed{P(\theta > \pi/3) = \frac{1}{2\sqrt{3}}}$$  

---

###  Conclusion   
Using a combination of  probability concepts, the law of total probability, and calculus ,  
we found that the probability of  $$θ$$ exceeding $$\frac{\pi}{3}$$  is  $$\frac{1}{2√3}$$ .  

This problem highlights how fundamental probability techniques can be used to analyze  geometric randomness .  

---

💡  Did you enjoy this problem? Check out more puzzles in the [Problems](https://jxtech-s.github.io/problems/) section! 
