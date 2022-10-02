---
excerpt: "In this post we give a primer on Odds, probability and the house edge. We give a worked example analysing the house edge when betting on red or black in European Roulette."
classes: wide
tags:
  - Gambling
  - Probability
  - Roulette
  - Football
---
# Primer on Odds, Implied Probability and the bookmaker's edge

In this article we outline some basic terminology and skills relating to the mathematics of gambling.
- We give a primer on odds vs decimal probability 
- We demonstrate that the bookmaker/casino odds do not always sum to 1
- We analyse betting on red/black in European roulette to determine the house edge


**Serious Note** This article is about gambling/betting. It is *not* an endorsement. I would never encourage gambling and do not gamble myself.

 ***If you don't like gambling why do you write about it?*** From a mathematical and data science point of view I think it is fascinating. I also think people in general have a very poor understanding of probability and may not realise some of the tricks bookmakers use. By writing about this I hope to educate people on these topics.



## How do odds work?

Bookmakers will often give you the *odds* for an event. The odds are meant to represent the likelihood of an outcome. They are easily explained with examples.

For a coin toss, the odds of getting a head are 1/1, read as 1 to 1. This means of the 2 possible outcomes, getting a head is just as likely as getting a tail. If you bet (wagered) 1 pound on heads, and the result of the coin toss is a head, your total return would be 2 pounds, this is 1 pound winnings and your 1 pound original bet. 

Let's see a real example.

At the time of writing, one bookmaker has the following odds for the UEFA Nations League - Scotland vs Republic of Ireland:
- Scotland: 19/20

- The Draw: 21/10 

- Republic of Ireland: 16/5 

So for Scotland to win the odds are 19 to 20. We interpret this as saying out of 39 (19+20) times, we would expect Scotland to win 19 of those and NOT win the other 20. (Be careful because NOT win is not the same as losing, because we also have the draw).
If you bet 20 pounds on Scotland to win, and they did win, your return would be 39 pounds - your 20 pound original bet and the 19 pound profit. 

The odds of Ireland to win are 16 to 5. This means if you bet 5 pounds, and they did win, your return would be 21 pounds, 16 pound winnings as well as your 5 pound original bet. 

One difficulty with odds presented like this is that they are hard to compare.

Another way of displaying odds is as **decimal odds**. The decimal odds tell you your total return on 1 unit bet. For example decimal odds of 1.35 mean that if you bet 1 pound and won, your total return would be 1.35 pounds, that is 1 pound of your original bet and .35 pounds (35 pence) of winnings. 

**To convert from fractional odds to decimal odds, treat the fractional odds as a fraction and add one.** 

### Let's see some examples. 
For tossing a head on a fair coin, we saw above that the fractional odds were $1/1$, and so the decimal odds are $1/1 + 1 = 2$. In other words if you bet £1 on heads, and it is a head, then your total return is £2 - this consists of your £1 original bet plus £1 profit.

For the football example above let's turn the fractional odds into decimal odds:
- Scotland: $(19/20   + 1) = (0.95 + 1) = 1.95$
- The Draw: $(21/10 +1)= (2.1 + 1) = 3.1$
- Republic of Ireland: $(16/5 + 1) = (3.2 + 1) = 4.2$

So if I bet 1 pound on Ireland to win, and they win, then the total amount I collect from the bookmakers is £4.20, this includes my £1 original bet and £3.20 profit. 

***To convert decimal odds back to fractional odds*** (this can be a little tricky because the decimal is not always precise, for example $1/3$ is not exactly equal to $0.33$), the process is to take the decimal odds and subtract 1, and then express that number as a fraction. 

For example for Scotland to win in the example above the decimal odds were $1.95$ so we subtract $1$ to get $0.95$, we can express this as a fraction as $95/100$. We could give the odds as this (read 100 to 95), but we can simplify this fraction even more by dividing the numerator and denominator by $5$ to get $19/20$, which matches above. (Note that fractional odds of 95/100 and 19/20 are identical, it is just a different way of writing them).

So, now we have covered different ways we can write odds (at least ways we might see in Europe). When we are talking about likelihoods of events occuring, we are really talking about probabilities. You might have studied probability at school. In the next section we will learn how to turn odds into probabilities.




**Converting odds to (implied) probability**

To convert fractional odds of an event to the probability of an event, we need the following formula:
$$ \text{Probability }= \frac{\text{Successful Outcomes}}{\text{Total Outcomes}}$$

So if the odds of $B$ occuring are given as $a/b$ then the probability of $B$ occuring is 
$$P(B) = \frac{b}{a+b}$$

For example, the odds of a head are $1:1$, so the probability of getting a head is $\frac{1}{1+1}=\frac{1}{2}=0.5$.

We can also go the other direction and convert from a probability to fractional odds: $\frac{P(b)}{1-P(b)}$, so for the example with tossing a head, we have $\frac{0.5}{1-0.5}=\frac{0.5}{0.5}=1$, so the odds are $1$ which we can write as $1 = 1/1$, odds of one to one. 

To convert decimal odds to a probability, we do $\frac{1}{\text{decimal odd}}$. So for example we saw above that for tossing a head on a fair coin, the decimal odds were $2$, and so to turn that into a probability we do $\frac{1}{2}=0.5$.

**Real Example**
Let's convert the odds for the Scotland Ireland game into probabilities (rounded to 3 decimal places). 
- Scotland: $20/39 = 0.513 $
- The Draw: $10/31 = 0.323 $
- Ireland: $5/21 = 0.238$ 

From the probability it is easy to see the bookmaker thinks Scotland are more than twice as likely to win than Ireland.

We might remember from school the teacher saying something like "the probabilities should sum to one". 
However here if we add the probabilities $0.513+0.323+0.238 = 1.074$, we get something bigger than 1. What is going on?! 


Well the probability we are using for the football example are not the *true* probability of the event occuring. It is the implied probability of the event occuring, based on numbers set by the bookmaker. The bookmakers can adjust their odds (downwards) to try to ensure they always make a profit. Let's look at this in more detail. 


## Running a book

We know that with a fair coin the probability of tossing a head is $0.5$ and a tail is $0.5$. These are the only two outcomes and they sum to $1$. 
The fractional odds are 
- Heads $1/1$
- Tails $1/1$

The decimal odds are 
- Heads $2$
- Tails $2$

As an exercise, you can turn these odds back into the (implied) probabilities and check they are indeed $0.5$. 

This would be a *fair* book. 

Imagine if I take bets from you on the outcome of these coin flips. Because you have no magical way of knowing how the coin will land, you will on average get it right  half the time, and wrong  half the time. This means half of the time I keep your pound bet, and the other half of the time I return your original bet and give you a pound profit. Then on average neither of us is any better or worse off. 


Also notice that in this situation if you bet a pound on heads AND a pound on tails, then no matter what the outcome you would end up no better off and no worse off. You would lose one of the bets (-1), but win the other (1 pound original bet + 1 pound profit), so your net is 0. 





### Distorting the probabilities...
As the bookmaker, I want to always profit. So I am going to offer you (decimal) odds:
- Heads: 1.9
- Tails: 1.9

This means if you bet 1 pound, you would collect 1.90, which is your 1 pound original bet and then only 0.90 profit.

The implied probability of getting a head from these odds is:
$\frac{1}{1.9} = 0.526$.

Let's just emphasise what is going on here. We both know that in reality the true probability of getting a head or a tail is 0.5. However the odds I have given you for getting a head correspond to a a bigger probability, of $0.526$, so the odds I have given you are saying this event is more likely than we really know it is. 

To put it another way, with tossing a coin and betting on heads, we know the true probability of losing is 0.5. However the odds I have given you make it look like your probability of losing is $0.474$. Your true risk of losing is higher than that, so by giving you these odds I am acting like your risk is less than it truly is. 

The analysis above is identical for tails. The implied probability for tails is $0.526$. 

If we sum the two probabilities we get $1.052$. This number is greater than $1$. The amount above $1$, the $0.052$ is the bookmaker's edge (margin, vig).

Notice that in the example above, if I bet 1 pound on both outcomes, I will end up losing money. 
I have bet a total of £2. One of my bets will win and I will collect a total of £1.90 - £1 original bet and £0.90 profit.  The other bet I will lose. So I now have £1.90, so I have lost 10p.

# Test yourself with an example

A European roulette wheel has 37 pockets with the numbers 0 - 36. The number 0 is coloured green. The odd numbers 1 - 36 are red and the even numbers 1 - 36 are coloured black. 

The fractional odds given by the casino for red and black are:

Red: 1/1
Black: 1/1

If you bet on red or black and the ball lands on 0 you receive no payout (there is no La partage rule at this casino!)

### Question 1: Find the decimal odds for Red and Black.
The decimal odds for Red: $1 + 1/1 = 2$. 
Similarly for Black. 

### Question 2: Find the implied probability for Red and Black
The implied probability for Red is $\frac{1}{\text{Decimal Odds}} = 1/2 = 0.50$
Similarly for Black.

### Question 3: What is the true probability for Red and Black?
There are 37 pockets (numbers) in total, and 18 of them are red so $18/37 = 0.486$ (3dp).
Similarly for black.

### Question 4: When betting on Red (or black) what is the house edge?
The true probability for Red is $18/37$, but the implied probability is $1/2$, and so: $1/2 - 18/37 = 0.0135$. 
One way to think of this is when you bet on Red there is an extra 0.0135 chance you will lose which you are not being fairly rewarded for by the odds. 
Similarly for black, so with red/black bets the edge is $2 \times 0.0135=0.0270$. 

We will dig more into roulette strategies (or lack of such things!) in a later post.




