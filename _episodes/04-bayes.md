---
title: "Bayes' Theorem"
teaching: 0
exercises: 0
questions:
- "What is Bayes' theorem? Why do we care?"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

In the previous episode, we have met *joint*, *conditional* and *marginal* probabilities, and we have 
met the sum rule, which tells us that the sum of all probabilies of a set of mutually exclusive 
probabilities needs to be equal to 1.

Let's revisit conditional probabilities. In order to compute a conditional probability, for example 
$$P($$:sunrise: \| :croissant: $$)$$, we had to first take the joint probability, 
$$P($$:sunrise:, :croissant: $$)$$, and then divide it by the *marginal* probability that croissants 
are served, $$P($$:croissant:$$)$$. We can write this out as an equation:

$$P($$:sunrise: \| :croissant: $$) = P($$:sunrise:, :croissant: $$) / P($$:croissant: $$)$$ 

or, reordering,

$$P($$:sunrise:, :croissant: $$) = P($$:sunrise: \| :croissant: $$) P($$:croissant: $$)$$ .

Notice, however, that we can do the same calculation for the other case, where we know that 
the coffee break will be during the morning, and we're trying to figure out whether we'll get 
to eat croissants:

$$P($$:croissant: \| :sunrise: $$) = P($$:croissant:, :sunrise: $$) / P($$:sunrise: $$)$$   

and when we do the same reordering, we get another equation that describes the joint 
probability of the two (croissants and morning breaks) together:

$$P($$:croissant: , :sunrise: $$) = P($$:croissant: \| :sunrise: $$) P($$:sunrise: $$)$$ . 

We have two equations for the same quantity, so let's equate them:

$$ P($$:sunrise: \| :croissant: $$) P($$:croissant: $$) = P($$:croissant: \| :sunrise: $$) P($$:sunrise: $$)$$    

There is an important subtlety about conditional probabilities here: the probability of eatint croissants 
given that we know there'll be a morning break is not the same as the probability that tomorrow's coffee break 
will be during the morning, given that catering has just told me that there'll be croissants.

> ## Exercise
>
> Convince yourself that the latter statement is true. Using the table from the previous episode, calculate
>
> * $$ P($$:sunrise: \| :croissant: $$) $$
> * $$P($$:croissant: \| :sunrise: $$) $$
>
> Can you explain why the two are not the same?
> Can you think of every-day examples for this, where it is obvious that $$P(A | B) \neq P(B | A)$$?
>
> > ## Solution
> > 
> > Let's calculate the conditional probabilities in both cases.
> >
> > * $$ P($$:sunrise: \| :croissant: $$) = 0.29 / (0.29 + 0.01) = 0.967 $$ 
> > * $$P($$:croissant: \| :sunrise: $$) = 0.29 / (0.29 + 0.06 + 0.25) = 0.483 $$
> >
> > So why are those two different? 
> > Let's look at a much simpler example: 
> > What's the probability that it's raining, given that there are clouds in the sky? 
> > Compare that to the probability that there are clouds in the sky, given that it is 
> > raining. They are not the same, because you *have* to have clouds for rain, but it 
> > can be cloudy without raining!
> >
> > {: .output}
> {: .solution}
{: .challenge}

### Bayes Theorem

We now have all the ingredients to write down Bayes' theorem. In face, we have already written a version 
above. While the emojis were fun, let's replace them at this point with the more generic characters "A" and 
"B". These are just placeholders for possible outcomes.

> ## Bayes Theorem
>
> Here's Bayes theorem in its common form:
>
> $$ P(A | B) = \frac{P(B | A) P(A)}{P(B)} $$
>
>
{: .callout} 

This is the same equation as we've written above, just with one of the marginal probabilities pulled to the 
other side. 

### Bayes Theorem in Scientific Data Analysis

How can we use Bayes' theorem in scientific data analysis? In the introduction, we established that 
we generally collect data about some natural process we would like to measure, and often we build a mathematical 
model for those observations. Think of the observation that an apple falls on the ground, which we can 
describe with the mathematical equations of Newtonian gravity.

However, we need to connect the data we collected (for example the velocity the apple had when it hit the ground) 
to the mathematical equations describing the physics of our universe (the Newtonian mechanics). 

Often, the physical model has parameters, say the gravitational constant of the Earth, that we are trying to measure. 
Let's say we've observed ten apples that fell out of the tree, and we've collected the speed upon impact on the 
ground for each of them. That's our data set, often denoted $$D$$, made up of ten individual measurements. We have 
a model, which we'll denote $$M$$, Newtonian gravity, which we are going to **assume** is the true process governing 
how apples fall out of trees (as anyone who has taken a General Relativity class will tell you, that assumption is 
only an approximation of reality, but for apples and trees, it's a pretty good one). In our current set-up, we're 
not arguing whether gravity exists and is governed by the equations that Newton wrote down (though we could do that 
too, but that's a problem for another episode). What we're trying to do is measure the Earth's gravitational 
constant, which is a **parameter**, often denoted $$\theta$$ of our model $$M$$.

Bayes theorem tells us how to relate those quantities to one another:

$$
P(\theta | D, M) = \frac{P(D | \theta, M) P(\theta | M)}{p(D | M)}   . 
$$    

Here, we are trying to calculate $$P(\theta | D, M)$$, or, in words, the probability of a parameter $$\theta$$, 
like the Earth's gravitational constant, given that we collected some data $$D$$ (the apples falling out of 
the tree) and assumed a model for our world $$M$$ (Newtonian gravity). 

This is often what we want to know: we want to know the effect a treatment has, or a cosmological parameter 
that tells us how the universe expands, and we want to know the probability of that parameter given that 
we've observed some data, which is known (because we've observed it). This quantity on the left-hand side 
of the equation is called the **posterior probability distribution**.

However, our data is never shiny and clean and perfect. There are always measurement errors, and experimental 
data generally displays a degree of randomness. While the physical model $$M$$ tells us what kind of mathematical 
equations we need to write down in order to describe the world, the first term on the right-hand size, 
$$P(D | \theta, M) P(\theta | M)$$, tells us how to relate the data we've collected to that physical model and its 
parameters. This is also called the **likelihood**, and it's part of the **statistical model** we are using to 
infer knowledge from our data. The likelihood generally describes our measurement errors. For example, the 
device I use to measure the velocity of our apples won't be arbitrarily precise. If it repeated the same experiment 
with the same apple under the same conditions, it would give me a slightly different value for the velocity. 
This uncertainty is something we need to account for, which is where the likelihood comes in.

The likelihood alone does not give us our answer: remember, we're interested in the probability of $$\theta$$, and 
we established earlier that $$P(A|B) \neq P(B|A)$$. To relate the two, we need the **prior**, $$p(\theta | M)$$. 
The prior describes our knowledge of the parameter $$\theta$$ before we collected the data. For example, we might 
have an idea of the Earth's gravitational constant from previous measurements, and we know that it's probably 
not negative (or we'd be actively pushed *away* from the ground). That kind of knowledge, about whether certain 
parameters are plausible, and information we have from previous measurements, can be encoded in this probability 
distribution. 

Priors are a key part of Bayesian statistics, and they're one reason why some people are suspicious of the 
framework as a whole: there is no objectively "correct" way to choose a prior for any given problem, and how to 
choose priors well is an ongoing field of research in statistics. Choosing priors injects a certain amount of 
**subjectivity** into the data analysis procedure, which scientists are naturally suspicious of (shouldn't science 
be as objective as possible?). Bayesian statisticians would respond to this criticism that not using priors is 
not technically an objective choice, either (because it corresponds to a specific prior), and that Bayesian 
statisticians are just more explicit about writing down their prior assumptions.

The latter is an important point: when showing results, write down your assumptions, including the priors you 
used to derive a posterior probability distribution. That way, readers can make sense of what you've done, and 
if necessarily repeat the calculation with a different prior.

There is one last term in this formulation of Bayes' theorem, the term in the denominator, $$p(D | M)$$. This is 
often called the **marginal likelihood** or sometimes the **evidence**. It is a bit of a weird quantity: the 
probability of observing the data (the apples falling off the tree), given the model (Newtonian gravity), but 
*for all values of the parameter $$\theta$$*. In practice, this is a normalization term.

Recall that probabilities need to sum or integrate to 1. This means that the marginal likelihood is defined as 

$$p(D | M) = \int_{\Omega}{P(D | \theta, M) P(\theta | M)}d\theta $$ 

to make sure that $$p(\theta | D, M)$$ integrates to 1. The marginal likelihood plays a big role in model 
comparison, where you are trying to decide which of two (or more) different models describes your data better
(for example, Newtonian gravity or General Relativity).

One important thing to note is that the marginal likelihood is a *constant* with respect to the parameter $$\theta$$.
This means that if all you're interested in is the relative probability of some parameter value $$\theta_1$$ being more 
probable than a different parameter value $$\theta_2$$, you can ignore the marginal likelihood, which is generally 
difficult to compute, and just write

$$P(\theta | D, M) \propto P(D | \theta, M) P(\theta | M)$$

{% include links.md %}


