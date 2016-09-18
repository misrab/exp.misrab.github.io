---
title: An Exploration of Basic Probability - Counting & Expectation
layout: blog
image: /images/prob1/3.png
date: 2014-11-02
excerpt: |
  In the first part of this series, I look at probability as
  counting, and expectation with non-numeric events. Can you tell
  me the expected value of red and blue?
---


# An Exploration of Basic Probability - Counting & Expectation

_Posted on November 11th, 2014_

## Introduction

I\'ve come across probability in all sorts of contexts:
in the social sciences, machine learning, a bit of measure theory,
functional analysis, and more. As such, it has become a set of
concepts and tricks I\'m acquainted with, but
haven\'t really spent much time absorbing in a unified way. Here I\'ll
try and highlight some very basic, but subtle points, just for
exploration\'s sake. I'll start a view of probability as simple counting,
and play with expectations in an uncommon setting. There will be the occasional
formality, but only when I think it adds to the exploration.

## Counting

Suppose we have events $$ \mathbf{X} = \{ A, B, C \} $$, and a probability
measure $$ P $$. Measures are easy, and you can read up on them [here](http://en.wikipedia.org/wiki/Measure_(mathematics)). A probability measure just sums to 1 over the space of
events. This is precisely counting: let's say in a 100 trials, $$A$$, $$B$$, and $$C$$ happen respectively 30, 20 and 50 times. We're not talking about the reason this happens; take itas a law of the universe. Then if we're looking at a [random variable](http://en.wikipedia.org/wiki/Random_variable) $$x$$, we have $$P(x = A) = 0.3$$, and so on. Counting :)

We could look at combinations of events, like $$P(A \cup B) = 0.5$$. The set of all these
possibilities $$ S = \{ \{ A, B\}, etc... \} $$ is formalized as a [$$ \sigma - field $$](http://en.wikipedia.org/wiki/Sigma-algebra). If you go through the definition, it's actually very reasonable.

I've found that these things are always presented as very matter of fact. But what
happens when we try and look at slightly funky things, like non-numeric events?

## Expectation

We presumably all know the formula $$ E(x) = \sum_{ x \in \mathbf{X} } x \cdot p(x) $$.
But what happens when we don't have numeric values? What's the expected value of
$$A$$, $$B$$, and $$C$$ in our case?

We could start by simply assign real numbers. For example, we could set
$$ (A,B,C) = (1,2,3) $$ or $$ (A,B,C) = (3,2,1) $$.
But then in the first case we have an expected value of
2.2, and in the second case 1.8, without changing the fundamental problem. This leads to,
as far as I know, a fundamental restriction when we want to play with numeric concepts like expected value or variance. Technically speaking, that is why we define them in terms of a **random variable**, a function from $$ \mathbf{X} \rightarrow \mathbf{E} $$
where $$ \mathbf{E} $$ is a measurable space, usually $$ \mathbb{R} $$. But this
doesn't tell us much about how we might think about assigning numbers to our events. Let's investigate this a bit further since we're already having so much fun.

I'll try to develop a bit of intuition concerning expectation when we _are_ using numbers, to see how we might want to make the leap from non-numbers. Consider now
$$ \mathbf{X} = \{ 1, 2 \} $$ with $$ P(1) = P(2) = 0.5 $$.

![probability histogram](/images/prob1/1.svg)

### Linearity in events

What happens if we play with our event values?

$$ \mathbf{X} = \{ 1, 2 \} \longrightarrow E(x) = 1.5 $$

$$ \mathbf{X} = \{ 1, 3 \} \longrightarrow E(x) = 2 $$

$$ \mathbf{X} = \{ 1, 4 \} \longrightarrow E(x) = 2.5 $$

It's not too hard to see from our formula for expected value that if we change
a given event's value by $$ \Delta x $$, we change expectation by
$$ \Delta x \cdot p(x) $$.

### Linearity in probabilities

What happens if we now play with assigned probabilities over fixed $$\{ 1, 2 \}$$? It's even more interesting now: since probabilities need to sum to 1, increasing an event's
probability means decreasing that of one or more others. In the simplest case (the complicated case really isn't complicated), we have

$$  \Delta E(x) = \Delta p(x) \cdot x + \Delta p(y) \cdot y $$

In conclusion, expectation looks like a **linear** function over both its event space and
their assigned probabilities. Nice! Linearity usually points to something like a
[vector space](http://en.wikipedia.org/wiki/Vector_space). Going back to our problem of
dealing with non-numeric events, we now have a slightly better idea of how we might want to convert them to numeric values in a way that makes sense. To be precise, if we're thinking of assigning $$A$$ to 1 or 4, we should be aware that the latter will pull
expectation up by a factor of 4 times the assigned probability.

### Norms and "Pre-processing"

Consider assigning $$ (A,B,C) = (1,2,3) $$, with equal probabilities of $$1/3$$. By our previous argument, $$C$$ contributes three times as much to expectation per apple of
probability. We're now comparing _between_ events. The idea of comparison might tempt us
to play with [metrics](http://en.wikipedia.org/wiki/Metric_(mathematics)) or even
[inner products](http://en.wikipedia.org/wiki/Inner_product_space), but really all
we need is norms. In this case, we have $$ ||C||_2 / ||A||_2  = 3 $$. Since we're working in $$ \mathbb{R} $$, we just have the ratio of absolute values.

The question then arises, might there be any purpose in converting non-numeric events to
a normed vector space other than $$ \mathbb{R} $$?  We could call this "pre-processing", since in any case we're ultimately taking a norm which leads to a real number. But there might some modelling advantages. A simple case would be $$ \mathbb{R^2} $$. Consider a point $$ A $$ at $$ (1,1) $$. We could translate it to $$(1,2)$$ or $$(2,1)$$; either
would change the $$2-norm$$ by the same amount.

![point translation](/images/prob1/2.svg)

In fact by using the $$2-norm$$ we're
defining an equivalence class on a circle. For example each point could represent (height, age), and we're defining a tradeoff function when it comes to probability expectation. Different norms lead to different tradeoff functions:

![unit norms](/images/prob1/3.png)

One could imagine first converting a non-numeric sample space into a
meaninful vector space with "probability" equivalence classes induced by
an appropriate norm.

## Conclusion

I'm still only at the beginning of this exploration. I hope I'm not being too naïve.
Some parts may seem banal, and I could be much more formal, but hopefully by looking at concepts in a down-to-earth way we'll encounter some interesting questions that I haven't come accross directly in the academic literature, such as we did with expectation and non-numeric sample space here.
