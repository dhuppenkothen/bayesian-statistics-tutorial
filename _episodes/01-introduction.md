---
title: "Introduction"
teaching: 0
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

**How do we infer information from data?**

This is a core question of any scientific research. How do we go from the data collected 
to knowledge about the world around us? Knowledge in this context could mean the result of a medical
study testing the efficacy of a new drug, it could mean the outcome of a physics experiment, or
using observations of exploding stars to tell us something about the expansion of the universe. 

There's a famous saying in statistics:

> ## Models
>
> "All models are wrong, but some are useful."
>
> (George Box)
>
{: .callout}

Nature is in general very complex, and so are our procedures for collecting data (whether they 
are telescopes, or medical studies, or lab experiments). We build models to try and make sense 
of these complexity. In astronomy, we might build a model of how the universe expands by writing 
down physics equations. But equations that describe the universe are not enough! They don't tell 
us how we can use the data to learn more about whether those equations make sense. 

One key element binding together **data** and **knowledge** is statistics. Statistics helps us
understand and take into account randomness in our measurement device and uncertainty about the
world around us. It helps us quantify how certain we can be in a result derived from data.

For statisticians, the equations that describe the world we live in are only a part of the *model*.
The other part are a number of equations that describe how we move from data to knowledge, and 
how we can describe the uncertainties and the randomness in our observations.  

This tutorial aims to give a short and gentle introduction into Bayesian statistics, one framework
of statistical inference and decision making that has become increasingly popular in recent years. 

> ## A Quick Census
>
> Let's do a quick round-up of everyone's knowledge. Go to this [anonymous survey][survey] and 
> click the answers that best describe your current state of knowledge. Don't worry, this is for 
> information only!
>
> If you're doing this at home, don't worry about the survey and just continue on! You can read 
> and skip sections at your leasure.
>
{: .challenge}

This tutorial owes a lot to previous Bayesian statistics tutorials at [Astro Hack Week][ahw],
especially Brendon Brewer's [tutorial][bayes2015] in 2015 and Ruth Angus' [tutorial][bayes2018] in
2018. It is also directly based on the paper ["Introducing Bayesian Statistics with M&Ms][mmpaper]
by Gwen Eadie et al (2019). Because what better way to learn statistics than through chocolate?  

[survey]: 
[mmpaper]: https://www.tandfonline.com/doi/full/10.1080/10691898.2019.1604106
[bayes2015]: https://github.com/AstroHackWeek/AstroHackWeek2015/tree/master/day4-day5-inference
[bayes2018]: https://github.com/AstroHackWeek/AstroHackWeek2018/tree/master/day2_bayesian_inference

{% include links.md %}
