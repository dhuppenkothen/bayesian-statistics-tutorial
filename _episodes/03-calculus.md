---
title: "Calculations with Probabilities"
teaching: 0
exercises: 0
questions:
- "What are the basic operations one can do with probabilities?"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

So far, we have only encountered a fairly abstract definition of what probabilities are, and two examples: 
coin tosses (a very classical example that statisticians love very much), and the weather.

Let's take a look at a different example, important for anyone who has ever been to a scientific
conference: **Will there be :cookie: at coffee break?**

When working with probabilities, we usually use the notation `P(outcome)` to describe a probability of an
outcome. The "P" stands for "probability of" whatever follows in the round brackets, which should be
an identifier of whatever outcome you are trying to calculate the probability of. That could be a
word, like `P(cookies)`, or it could be a variable shorthand for that outcome, say `P(c)`, or
something else. For fun, let's use `P(`:cookie:`)`.

Let's say there are three things that could be served at coffee: :croissant:, :cake:, and of course :cookie:. 
But snacks are served only once per day, either during the morning coffee break (:sunrise:) 
or the afternoon coffe break (:sleeping:)!

> ## Exercise
>
> How many possible outcomes are there? Write down all possible
> outcomes.
>
> > ## Solution
> >
> > There are six possible outcomes:
> > * :croissant: during a :sunrise: coffee break
> > * :croissant: during a :sleeping: coffee break
> > * :cake: during a :sunrise: coffee break
> > * :cake: during a :sleeping: coffee break
> > * :cookie: during a :sunrise: coffee break
> > * :cookie: during a :sleeping: coffee break.
> > 
> > {: .output}
> {: .solution}
{: .challenge}

### Joint and Conditional Probabilities

Let's say I am involved with the organization of the conference, and have had extensive contact with the 
catering company. Therefore, I have some idea when breaks are going to be, and what's going to be served 
during them. I'm pretty forgetful, though, and not good at making notes, so I only remember the overall 
number of morning/afternoon coffee breaks, and which things are more likely to be served when:

|             | :cookie: | :cake: | :croissant: |
|-------------|----------|--------|-------------|
| :sunrise:   | 0.25     | 0.06   | 0.29        | 
| :sleeping:  | 0.25     | 0.14   | 0.01        |

Cookies are always popular, no matter the time of day. Croissants are definitely a breakfast food, so 
you'd rarely get them in the afternoon. Conversely, perhaps cake are better served in the afternoon, so 
you would get those more often then. 

So what does this table tell us? For each of the six possible outcomes, it tells us the probability of 
that outcome happening on a given day. So if I wanted to know whether there'd be a coffee break in the 
morning with cookies, I could look up the :sunrise: and :cookie: cell, and find that there's about a 
25% chance that this might indeed happen. 

In mathematical terms, we say that this is "the **joint probability** of :cookie: **and** :sunrise:", 
written as $$P($$:cookie:, :sunrise:$$)$$. The joint probability is the probability of both outcomes 
being true at the same time.

One important property of probabilities is that the 
probabilities of all possible outcomes must sum to 1. 

> ## Sum Rule
> 
> When $$A$$ and $$B$$ are mutually exclusive outcomes, then then $$P(A) + P(B) = 1$$.
>
> This implies that $$0 \leq P(A) \leq 1$$, and $$P(B) = 1 - P(A)$$.
>
> Negative probabilities do not exist.
>
>
{: .callout}


What if we wanted to know the overall probability of getting cookies, no matter which break? To calculate 
this, we take the probability of getting :cookie: during :sunrise:, and the probability of getting :cookie:
during :sleeping, and add them together:


$$P($$:cookie:$$) = P($$:cookie:, :sunrise:$$) + P($$:cookie:, :sleeping:$$) = 0.25 + 0.25 = 0.5$$

The total probability of having cookies served during a coffee break is 0.5. This means that in half of 
*all* coffee breaks, you will be served cookies. This is called the **marginal probability** and describes 
the sum (integral) over a number of possible outcomes in a joint probability. 
 
There is an important subtlety here, though. Say you can see the outside of the room, where the catering 
company is setting up morning coffee. You're excited, because it means you get coffee during the morning 
today! What's the probability that cookies are going to be served with this break? 

Is it 0.25, as we've initially calculated? Or is it 0.5, as we have just seen? 

> ## Exercise
>
> Find the probability of being served cookies, given that you know that today's coffee break will be 
> a :sunrise: one. Once you're done, share your answer online in the [survey][survey]. 
>
{: .challenge}

The answer is neither! The probability of being served cookies has changed, because we already *know* 
that there's a morning coffee break today. There will definitely not be an afternoon coffee break today, 
and so the entire bottom row of the table above collapses to zero. But we have said above that the sum 
rule implies that the sum of all mutually exclusive options must sum to one! 
This all outcomes involving an afternoon break have become impossible, those probabilities are all zero. 
We thus need to re-normalize the top row so that it normalizes to 1. 

This is called a **conditional probability**, written as $$P($$:cookie:$$|$$:sunrise:$$)$$ and pronounced 
as *the probability of :cookie: **given** that :sunrise: is true*. Let's do the maths:

$$P($$ :cookie: \| :sunrise: $$) = 0.25 / (0.25 + 0.06 + 0.29) = 0.41 $$

How did we arrive at this conclusion? We have taken the joint probability of both :cookie: and :sunrise:, but 
we've said that this is not the correct probability, because the other option (cookies during ther afternoon) 
is impossible. In order to figure out the probabilities that we'll get cookies during the break, given 
that we *know* the coffee break will happen in the morning, only depends on the three options in the top 
row, and so those are the only three options available to us. If you add them up, you get

$$ 0.25 + 0.06 + 0.29 = 0.6 $$

which, incidentally, is the *marginal* probability that a coffee break will occur in the morning (so 60% of 
all coffee breaks will occur in the morning). Because we know that we'll have a morning coffee break, we 
need to re-normalize those three probabilities so that they add to 1. For the case of :cookies:, this is exactly 
what the equation above does, by dividing $$P($$:cookie,:sunrise:$$)$$ the sum of all three probabilities.

> ## Exercise: Joint, marginal and conditional probabilities.
>
> Let's practice this! Write down the values for the following three 
> probabilities:
>
> * $$P($$:cake:, :sleeping:$$) = $$
> * $$P($$:sunrise: \| :croissant: $$) = $$
> * $$P($$:croissant:$$) = $$
> * $$P($$:cake: \| :sunrise: $$) = $$
>
> >  ## Solution
> > 
> > Here are the different probabilities: 
> >
> > For the first example, you can read the joint probability straight off the table:
> > * $$P($$:cake:, :sleeping:$$) = 0.14$$
> >
> > The second case is a *conditional* probability, so we need to re-normalize the 
> > the probability that it's a morning session by the fact that we know we'll get 
> > croissants: 
> > * $$P($$:sunrise: \| :croissant: $$) = 0.29/(0.29+0.01) = 0.967$$
> >
> > For the third example, we need to calculate the *marginal* probability that we'll 
> > be served croissants, so we need to add up the probabilities for being served 
> > croissants in the mornings and in the afternoons: 
> > * $$P($$:croissant:$$) = 0.29 + 0.01 = 0.3$$
> > 
> > The last example is yet another example of a conditional probability, here that
> > we'll get cake in a morning break, given that we can see them already set up for 
> > said morning break: 
> > * $$P($$:cake: \| :sunrise: $$) =  0.06 / (0.25 + 0.06 + 0.29) = 0.1$$

> > {: .output}
> {: .solution}
{: .challenge}
     

{% include links.md %}


