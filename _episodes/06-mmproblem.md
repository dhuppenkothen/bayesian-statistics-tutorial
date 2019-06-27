---
title: "Inferring the Fraction of Blue M&Ms, Part 1: Problem Set-Up"
teaching: 0
exercises: 0
questions:
- "What statistical questions can we ask about M&Ms?"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

Now that we've defined Bayes' theorem in the previous episode, we're going to 
use it for a real-world problem. Since all that talk of snacks during the episode 
on conditional probabilities has made me hungry, we're going to talk about M&Ms. 

M&Ms are chocolate candies that come in bags, where each bag has some number of 
different M&Ms. They come in different types (for example, some have peanuts in them, 
some have almonds, and some no nuts at all), and in different colours. 

> ## Collecting Questions
>
> Given a bag of M&M candies, what kind of information can you learn from the M&Ms 
> in that bag? Can you think of a question you might be able to answer by exploring 
> the contents of your bag? 
> 
> Write down an idea, then share and discuss with your neighbour. What data would 
> you need to collect from your bag of M&Ms to answer your question? 
>
> 
> **Note**: Don't open the bag yet! We'll get to that in a little while. 
>
{: .challenge}

There are a number of different questions you might be able to answer with a bag of M&Ms.
In this lesson, we will be answering a specific one :

> ## Our Research Question
>
> What is the percentage of **blue M&Ms** produced at the factory?
>
{: .callout}

To answer this question, we will be using Bayes' theorem and one bag of M&Ms. 
Here, our **data** $$D$$ will be the M&Ms in our bag, along with their colour (for 
simplicity, we will use two colours: "blue" and "not-blue"). The **parameter** $$\theta$$ 
we are interested in here is the percentage of blue M&Ms produced at the factory.

We will need to define some additional details about the problem, particularly the likelihood 
and the prior, but let's do a little exercise first:

> ## Some Initial Questions
> 
> 1. In the data visualization you have learned that there are different types of data. 
> What type of data, do you think, are M&Ms? 
> * continuous
> * ordinal
> * categorical
> 
> If you don't remember what those words mean, you can take a look at the brief discussion 
> about types of data in the [visualization tutorial][dataviz].
>
> 2. How will you record the data?
> 3. Will you draw M&Ms out of the bag with replacement or without?
> 4. How might we model the probability of drawing a blue m&m?
>
> > ## Solution
> >
> > 1. Our data is categorical data: we have two different colours: blue and not-blue, 
> > and we are measuring the probability of obtaining each category when we draw an 
> > m&m out of the bag. 
> > 2. We will record the data in a [table][mmtable] so that we can then continue to 
> > use it.
> > 3. We will be sampling without replacement, that is, once we draw an M&M out of the 
> > bag, we won't put it back inside.  
> > 
> > {: .output}
> {: .solution}
{: .challenge}







[mmtable]: 
[dataviz]: http://huppenkothen.org/data-visualization-tutorial/08-types/index.html

{% include links.md %}

~                                                                               

