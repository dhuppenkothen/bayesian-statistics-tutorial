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

Here's the basic problem we're going to talk about today: You have a bag of M&Ms, and you 
want to know how many blue ones are in it. Easy, right? You open the bag, and count all the 
blue ones! But what if you have a [10 pound bag][mmbag] of M&Ms? Counting them all would take 
you ages, wouldn't it? Or what if you had several bags. The exact number of blue M&Ms as well 
as the total number of M&Ms in each bag might vary! So really, what we need is a model of the 
*average* number of blue M&Ms per bag. We don't just need any model, but we need a *statistical* 
model that describes the number of blue M&Ms we would get out of a bag of M&Ms given some 
underlying true fraction of blue M&M that were produced at the factory.

So, in short, our research question for today is this: 

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
> > 2. We will record the data in a [webform][mmform] so that we can then continue to 
> > use it.
> > 3. We will be sampling without replacement, that is, once we draw an M&M out of the 
> > bag, we won't put it back inside.  
> > 
> > {: .output}
> {: .solution}
{: .challenge}



[mmform]: https://forms.gle/eoHwWziWPq2LfPgG9
[mmbag]: https://www.mymms.com/product/bulk-mms-candy-10-lb.do?sortby=ourPicksAscend&refType=&from=fn&ecList=7&ecCategory=100601
[dataviz]: http://huppenkothen.org/data-visualization-tutorial/08-types/index.html

{% include links.md %}

~                                                                               

