---
title: "Probabilities, Frequencies and More"
teaching: 0
exercises: 0
questions:
- "What is the difference between a probability and a frequency?"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

What is a *probability*?

There isn't a single answer to this question, and any answer we might 
give is complicated by the fact that our every-day use of words like 
*probability* and *likelihood* does not necessarily match what statisticians mean when they use the
same words.


## Probabilities as Frequencies

In statistics, there are two basic ideas of what probabilities are. One line of thinking defines
probabilities as *frequencies*: for example, if I flip a coin one hundred times, how often will it
land heads up? In this line of thinking, to calculate a probability, you run an experiment very many
times (for example your coin toss), and then record the number of times each outcome appears. The
*probability* of each outcome is then defined as the fraction of times a certain outcome appeared
compared to the total number of experiments.

In the coin toss example, let's say we throw a coin ten times, and record the following sequence:

H H T H T T H T H H

Here "H" stands for "heads" (i.e. the side of the coin that has someone's head on it) and "T" stands
for "tails" (the side of the coin without a head). If you sum up the number of times that heads came
up, you find that six out of ten coin tosses showed heads, and four out of ten showed tails. 

So, now I can ask you the question: what is going to come up on the next coin toss? Heads or tails? 

Given the data you've gathered above, you might calculate the following probabilities:

* heads = 6 out of 10 = 6/10 = 0.6
* tails = 4 out of 10 = 4/10 = 0.4

You would answer that it's slightly more probable that the next coin toss is a heads than a tails.
Of course, this coin toss experiment suffers from an important shortcoming: we only tossed the coin
ten times! That's not a lot of experimental data, and so the limit becomes important: probabilities
are generally defined as frequencies in the *limit of very many repetitions* of the same experiment.

This is the core idea of **frequentist statistics**.

## Probabilities as Plausibilities

This definition of probability is extremely useful, but it has an important drawback: you can only
define probabilities for quantities where you can repeat the same experiment very many times. 

Here's a different question to ponder: What is the probability of rain tomorrow? 

This is a different question, because you *can't* repeat the same experiment very many times, like
you could with the coin toss. The weather tomorrow will depend on the overall climate, on your
location on the Earth, and on the season (and probably some other factors I can't think of right
now). How would you do the same experiment many times? 

In frequentist statistics, this problem often gets solved by the way of *thought experiments*: in
practice, we can't repeat the same experiment many times, but imagine we could. What are the
frequencies you would get if you repeated tomorrow many times and recorded the weather every time?

There is another way to answer this question, but it requires us to define *probability*
differently. What if instead of frequencies, probability described the *plausibility* of something
happening? How *reasonable* is it that it'll rain tomorrow? To answer that question, you might say
"Well, I know I am in Amsterdam, and Amsterdam is generally pretty rainy, so it's pretty plausible
that it'll rain tomorrow". This kind of knowledge is called a *prior*, which we will explore more in
later episodes.  

Plausibilities have the advantage that we can write them down for things that aren't inherently
random, like our coin toss. They're a core part of what is called **Bayesian statistics**, after
Reverend Thomas Bayes, who first came up with some of the core ideas in this area of statistics. 


## Which is better?

In short, neither. Frequentist and Bayesian statistics are often presented as fundamentally opposite
views of statistics, and are often pitched against one another (and there are some very strong
opinions held on either side!). 

In practical terms, don't get too hung up on ideology. Bayesian statistics has some significant
advantages for a number of problems, but that doesn't necessarily mean it is always the most
*useful* thing to do in practice.

> ## Know Your Assumptions
>
> In practice, it is often the most valuable course of action to pick the approach that will yield
> trustworthy results while also being computationally feasible, regardless of which statistical
> tradition this approach is rooted in. 
>
> However, in either case, it is crucially important to **know the assumptions your chosen method
> makes about your data and about the structure of your problem**. There are many standard methods
> that make strong assumptions about what your data looks like, but are employed with data sets that
> break those assumptions. When you do that, you have to make sure that the results you get are
> still valid and trustworthy (for example using simulations).
>
> It is equally important to **write your assumptions down** wne you publish your results. 
>
{: .callout}


> ## Examples of Probabilities
>
> Can you think of examples of probabilities defined as frequencies? Can you think of examples of
> probabilities that can't be defined as frequencies? 
>
> Write down an example for each, then share and discuss with your neighbour?
>
{: .challenge}


{% include links.md %}


