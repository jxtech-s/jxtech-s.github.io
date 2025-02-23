---
layout: splash
title: "Chess Tournament I"
date: 2025-02-23
categories: [Probability, Statistics, Problems]
tags: [Probability, Uniform Distribution, Triangle, Integration]
math: true
---
###  Problem Statement   

A chess tournament has 128 players, each with a  distinct  rating. Assume that the player with the  higher rating always wins  against a lower rated opponent and that the winner proceeds to the subsequent round. What is the probability that the highest rated and second-highest rated players will  meet in the final ?

 Original Problem Link:  [Click here](https://www.quantguide.io/questions/chess-tournament-i)  

---

###  Solution 

Before proceeding to the question, let's think of the following situation -  
Initially, 128 people are divided into 2 groups of 64 people each.  
In every round, each group will play within itself (say each guy plays with the guy beside him). How will a group play within itself?  

Consider group A with $$ A_1, A_2, A_3, A_4, \dots, A_{63}, A_{64} $$.  
Let's say that adjacent people play chess with each other. Then the games will be:  

 $$ (A_1 - A_2), (A_3 - A_4), \dots, (A_{63} - A_{64}) $$

From each game,  one person (with the higher skill) will win .  
Thus, after the first round, we will have  32 players remaining .  

This process will go on until only  one guy remains in each group , and that person will play with the person from another group to decide the  final winner .

Now, try to convince yourself that this model is  exactly the same  as the situation given in the question.  
How? 🤔 

- If the  initial distribution  of people among  Group A and B , and the  arrangement of people within both groups  are all  random , it will consider all possible plays between every player.
- Each  unique initial arrangement corresponds to a unique gameplay .
- Since by  randomizing the initial group allotment , all possible distributions of people in Group A and B are considered, it means  all possible gameplays  are also considered. This exactly models the given problem.

---

### Key Observation  

In our model of the gameplay, the  highest-rated and second-highest-rated player  will  face off against each other   only when they are in different groups initially .  

This problem is now much simpler, effectively reducing it to:  

>  In how many ways can I arrange 128 people in 2 groups (their position within the group is unique), such that 2 particular people are always in different groups?

---

### Solving the Sub-Problem  

First, let's allot the highest player and second-highest player to each group.  
There are  2 ways  of doing this:  
-  Highest -> Group A, Second-Highest -> Group B   
-  Highest -> Group B, Second-Highest -> Group A   

Now, once this is done:  
- Out of the remaining  126 people , select  63  people for Group A.  
- The remaining  63  go to Group B.  
- Now, we must  arrange the people within each group itself , thus another  $$ (64!) \times (64!)  $$ (one for each group).

Our final expression for the  favorable cases  becomes:

 $$
n(A) = 2 \times \binom{126}{63} \times (64!) \times (64!)
 $$

where  $$ A $$ is the event described above.

---

### Computing the Probability  

To find the probability of this arrangement, we must compute the  total number of possible arrangements .  
Clearly, this is  $$ 128! $$ How 🤔 ?  

- Assume a partition after $$ P_{64}  $$  (representing the end of Group A and the beginning of Group B) exists, to seperate groups A and B.
- We can linearly arrange all 128 people in $$128!$$ ways. Thus each combination will represent a unique gameplay.

Thus,  

 $$
n(S) = 128!
 $$

The required probability is:

 $$
P(A) = \frac{n(A)}{n(S)}
 $$

Substituting values:

 $$
P(A) = \frac{2 \times \binom{126}{63} \times (64!)^2}{128!}
 $$

Expanding the combination formula:

 $$
\binom{126}{63} = \frac{126!}{63! \times 63!}
 $$

Thus:

 $$
P(A) = \frac{2 \times 126! \times (64!)^2}{63! \times 63! \times 128!}
 $$

Expanding $$ 128!  $$ as $$ 128 \times 127 \times 126!  $$:

 $$
P(A) = \frac{2 \times 126! \times 64! \times 64!}{63! \times 63! \times 128 \times 127 \times 126!}
 $$

Canceling $$ 126! $$:

 $$
P(A) = \frac{2 \times 64! \times 64!}{63! \times 63! \times 128 \times 127}
 $$

Using:

 $$
\frac{64!}{63!} = 64
 $$

 $$
P(A) = \frac{2 \times 64 \times 64}{128 \times 127}
 $$

Simplifying:

 $$
P(A) = \frac{64}{127}
 $$

---

### Final Answer  

 $$
\boxed{\frac{64}{127}}
 $$

Thus, the probability that the  highest-rated and second-highest-rated players meet in the final  is  $$ \frac{64}{127}  $$.
---

💡  Did you enjoy this problem? Check out more puzzles in the Problems section! 
