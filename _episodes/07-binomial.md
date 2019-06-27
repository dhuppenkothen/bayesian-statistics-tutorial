---
title: "M&M Problem, Part II: The Likelihood"
teaching: 0
exercises: 0
questions:
- "What is the likelihood for the fraction of blue M&Ms?"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

In the last few episodes, we have talked about probabilities, Bayes' rule and probability distributions. Then we have 
set up our M&Ms research question.

It is now time to put our new knowledge to work!

Let's remind ourselves of Bayes' rule:

> ## Bayes' rule
> 
> $$ P(\theta | D, M) \propto P(D | \theta, M) P(\theta | M) $$
>
>
{: .callout}

We would like to estimate $$\theta$$, the number of blue M&Ms produced at the factory. To do that, we need to 
figure out the two terms on the right-hand side:
* the **likelihood**, $$P(D | \theta, M)$$, and
* the **prior probability**, $$P(\theta | M)$$

In this episode, we're going to talk about the likelihood. 

The likelihood describes the probability of observing a certain data set, given that we assume a model to be 
true. Let's assume we *know* that the true fraction of blue M&Ms produced at the factory is 0.5, so half 
of all M&Ms that are being produced will be blue. What can we say about the number of M&Ms?

> ## Number of blue M&Ms per bag
>
> Imagine that you had 10 bags with 50 M&Ms each. What will the number of M&Ms be in each bag?
> Will it always be the same?
>
> What could affect whether the number of M&Ms in each bag might be the same, or different?
>
>
> > ## Solution
> >
> > The number of blue M&Ms per bag will **only** be the same in each bag if that number is
> > carefully counted out before the bags are mixed. In practice, that seems unlikely, because 
> > it would produce a lot of extra work. It is more likely that there's a huge box of M&Ms of 
> > all colours, and a machine scoops out a handful of them into a bag.
> >
> > This means we do *not* expect the number of M&Ms to be the same in each bag. However, 
> > we expect that if we open *many* bags, then on average 50% of all the M&Ms we counted 
> > should be blue.
> >
> >{: .output}
>{: .solution}
{: .challenge}

The likelihood tells us how we go from the known fraction of M&Ms, $$\theta = 0.5$$, to the number of 
blue M&Ms per bag. But what equation do we need to write down to do this? 

Let's first start with our actual observables, i.e. the things we can measure about a bag of M&Ms. As 
we've said before, we *assume* we only have two colours: blue and not-blue. Like *all* models, this is a 
simplification of reality, but if we only care about the blue M&Ms, that's okay. If we suddenly also 
cared about the green M&Ms, we would have to make our model more complicated (if you're truly curious, the 
last episode in this lesson, on Bayesian hierarchical modelling, also tackles that question).   

In practice, there are two numbers we measure: the number of blue M&Ms, let's call those $$k$$, and the number 
of not-blue M&Ms, $$f$$. Because those are the only two possible outcomes of drawing an M&M out of the bag, 
together they make up the total number of M&Ms in the bag, $N$.  

Every time you draw an M&M out of a bag, you get one of two outcomes: blue or not-blue. In a more statistical 
language, a draw of an M&M out of a bag is called a **trial**, drawing a blue M&M is called a **success** (a 
not-blue M&M is called a **failure**). You can do this $N$ times and then record the number of successes, $k$. 

Let's assume that there's an underlying fraction $$\theta$$ that are produced at the factory. What's the 
probability of drawing a blue M&M out of the bag? Well, it's just $$\theta$$. Because our set-up only has 
two outcomes, and probabilities must sum to 1, the probability of having a not-blue M&M is therefore 
$$1 - \theta$$. 

So what's the probability of drawing a blue M&M, followed by a not-blue M&M? This will be the *joint* probability 
of first drawing a blue M&M, and then drawing a not-blue M&M, which can be written as

$$p( bn | \theta) = p(b | \theta) p(n | \theta) = \theta (1 - \theta)$$

So we've just multiplied the probability for getting a blue M&M with the probability of getting a not-blue 
M&M. In the equation above, $$bn$$ is just a placeholder for the blue + not-blue sequence we just described.

> ## Exercise
>
> What is the probability of the sequence: b b n n n b n ?
>
> > ## Solution
> > 
> > Like in the example above, we can string together the probabilities:
> >
> > $$ p(bbnnnbn | \theta) = (1 - \theta)(1-\theta) \theta \theta \theta (1-\theta) \theta = (1-\theta)^3 \theta^4 $$
> > 
> > {: .output}
> {: .solution}
{: .challenge}

For any given sequence of draws out of the bag, we can write down the probability of that sequence as the 
product of the probabilities for each of the individual draws. So for a sequence with $$k$$ blue M&Ms,
 $$f$$ not-blue M&Ms and therefore a total $$N = k + f$$ M&Ms, we can write the probability of that 
exact sequence as

$$ p(s | \theta) = \theta^k (1 - \theta)^{(N-k)} $$

That's great, you might say, we're done! We know what the probabiity is! However, there is one crucial element 
missing! This probability tells you the probability of **that *exact* sequence**. But if we pour the contents 
of a bag of M&Ms onto the table, then what? Have we first drawn a blue M&M? A not-blue M&M? Will it depend on 
whether we draw a blue or not-blue M&M first? It shouldn't. The probability of the sequence "b n b" is the same 
as for the sequence "b b n" and also for the sequence "n b b". The equation above doesn't account for that, 
so we need an extra factor that adjusts the probability for the fact that I could have drawn any of those 
three sequences. This factor is $${N \choose k}$$, pronounced "n choose k" and also called the **binomial 
coefficient**. It can be written out as

$$ {N \choose k} = \frac{N!}{k! (N-k)!} = \frac{N * (N-1) * ... * 2 * 1}{k * (k-1) * ... * 2 * 1 * (n-k) * (n-k-1) * ... * 2 * 1} $$

The "!" symbol is called a "factorial", and short-hand for writing out a product of all the numbers from that number
to 1 (note that $$0! = 1$$). This fraction is the adjustment you need to do to make sure you don't count "n b b", 
"b n b" and "b b n" as separate cases. 

> ## Exercise: Binomial factors
>
> Convince yourself for the three-outcome case that the binomial factor accurately adjusts 
> the probability.
>
> > ## Solution
> >
> > In the above case, we have three possible sequences we could draw. For each sequence, 
> > the probability is
> > 
> > $$p(s | \theta) = \theta^2 (1-\theta)^1 $$ 
> > 
> > We want to know the probability that **any** of those sequences happen, which we can 
> > calculate by summing together the probability for each of the three outcomes (which 
> > is the same as multiplying the probability above by $$3$$. Can we use the binomial 
> > coefficient to arrive at the same answer? 
> > 
> > $$ {N \choose k} = {3 \choose 2} = \frac{3 * 2 * 1}{2 * 1} = 3 $$
> > 
> > Therefore, the probability of having two blue M&Ms and one not-blue M&M in any set 
> > of three M&Ms is
> > 
> > $$ p(b=2, n=1 | \theta) = {3 \choose 2} \theta^2 (1-\theta)^1 $$
> > 
> > {: .output}
> {: .solution}
{: .challenge}


We now have all the ingredients to write down the probability of getting any set of $$k$$ blue 
M&Ms in a set of $$N$$ total M&Ms:

> ## Binomial Probability Distribution
> 
> $$p(k | \theta, N) = {N \choose k} \theta^k (1 - \theta)^{(N - k)} $$
>
> This is also called the **binomial distribution**, and will serve as our **likelihood**.
>
{: .callout}




{% include links.md %}
 

