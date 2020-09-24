---
layout: single
title: Volumes of spheres in more general discrete metrics
date: 2019-04-20 14:00:00 +0530
excerpt: On our ISIT 2019 paper on a new technique to find said volume
tags: coding-theory information-theory
categories: academic
comments: true
toc: true
toc_sticky: true
header:
  teaser: 'https://lh3.googleusercontent.com/kk18j989Eiks_OrirayG6o2MY6XMKLJ6VjqW3p1od0tJnn9_Vut3BHepPhbNKFxyi90Tty1Ji3tgMitM8_3PNlElGt38BGcI49B2aQa9_7auSEuh9qWfFNc9o8N5CmEeDYoo_teOcLA=w2400'
---
Recently I co-authored a [paper](/assets/pdfs/Lee_metric.pdf) with [Prof Adrish Banerjee](#), which we submitted to [ISIT 2019](https://2019.ieee-isit.org/), and I thought I would go over the key ideas in the paper as a blog post. Our main concern was to find out the volume of spheres in discrete metrics, and applications of the method to the Lee metric.

# Background

Why would it be an interesting problem to talk about the Lee metric and bounds of the kind that we were looking for? It turns out that there are quite a few applications for results of this sort.

A bound on the volume of a sphere in a discrete metric is used to find bounds on the limits of reliable communication over a channel (more on that later). We actually see this in the paper itself - the moment we obtain an upper bound on the volume of a sphere in the Lee metric, we could use known results to immediately find analogues of the binary Hamming, Elias-Bassalygo and Gilbert-Varshamov bounds in the case of the Lee metric (more on all of these later). The basic utility of bounds on the limits of reliable communication over a channel should be clear - it gives people who design communication protocols something to aim at, and if such a design hits the upper bound, we know that one cannot do better, at least from the rate point of view (one could still improve things like encoding-decoding efficiency etc.). There are other examples too - consider the result of [another paper](/assets/pdfs/Shared_randomness.pdf) that I was a co-author on that was also accepted to ISIT, where we showed that if the capacity under vanishing average error of a channel does not equal the zero-error capacity (both of these terms will also be talked about later in slightly more detail) of the channel, we need at least $$\log(n)$$ bits of common randomness, where $$n$$ is the blocklength of the code, to communicate reliably at capacity over the channel. Common randomness being a valuable resource (it is hard to generate and distribute such randomness), such a bound is good to know. How to show such a gap exists? We need an upper bound on the capacity of the kind that our results help us find.

This is the thing that brought our attention to this problem in the first place. We already knew the common randomness result, and we knew that the gap exists for the Hamming metric, but we thought it would be interesting to show that the gap exists for a more general channel - enter the Lee metric.

## Why is a metric important?

Before proceeding further, let me quickly talk about metrics and why they are useful in information and coding theory. So a major subfield of information theory involves finding the limits of reliable communication over a particular channel. Now *reliable* can be defined in various ways - two of which are
* we want the *average* error to go down to zero when we use the channel multiple times
* we want the error to be *exactly* zero for all channel uses

In most cases, the maximum rate at which we can transmit information in the first case will be higher than the maximum rate for the second case. Now, any transmission is done using an *encoder-transmitter* pair and a *receiver-decoder* pair, with a (possibly noisy) channel in between. In recovering the transmitted data from the noisy data at the receiver, it makes intuitive sense that the decoder should choose the most probable transmitted codeword given the model of the channel noise and the received data, an idea called **M**aximum **L**ikelihood (ML) decoding. This is where the metric comes in. If the channel noise model is sufficiently 'nice' we can replace the ML decoding at the decoder by using a metric (which is just a measure of distance) such that choosing the nearest neighbour in the set of all possible transmitted codewords to the received data, we get the same result as what we would get if we were to use ML decoding. When this happens, we say that the metric is *matched* to the channel under consideration. Note that the metric that will be used depends crucially on the encoder, noise model of the channel, and the decoder. This idea will become clearer in the next section.

## The Hamming and the Lee metrics 

Two metrics that have been studied relatively deeply in the literature are the Hamming metric and the Lee metric. The Hamming metric is a very simple metric - given two $$n$$-length words $$a$$ and $$b$$, it counts the number of differences between them. It is useful in cases where, given any two distinct *symbols* (not words) $$a$$ and $$b$$, the probability that the channel corrupts $$a$$ to $$b$$ is the same, and this probability remains the same if the pair $$(a, b)$$ is replaced by any other distinct pair $$(a',b')$$. Even though this metric is really simple, it can be used to describe a large class of encoder, decoder and channel combinations, and thus has been the most well-studied metrics in information and coding theory. The Lee metric is useful whenever symbols closer together are more probable to corruption than symbols further apart, and the decision of the 'closeness' of two symbols is made by arranging the symbols in a circle (for example, the first symbol and the last symbol are considered adjacent, which wouldn't be the case if they were on a line).[^1]

## Rate-Distance Trade-offs

Another interesting concept is that of a rate-distance trade-off. It again makes intuitive sense to say that if two codewords are far apart in a suitable metric, then the probability that the channel will confuse the two is low. So, to protect against as many errors as possible, we want our codewords to be as far off from each other as possible. However, in a finite space, we can only pack so many codewords that are all pair-wise more than a given distance away. So, given the number of errors a code can handle, we get a bound on the number of codewords we can use. If we use $$n$$-length code, the number of such codewords grows exponentially in $$n$$, and therefore it makes sense to define the rate as $$\log \mathcal{M}(n)/n$$, where $$\mathcal{M}(n)$$ is the number of possible $$n$$-length messages. In the case of the error being exactly zero, we want there to be no codewords in a sphere around a given codeword. For average error going to zero, we can allow small intersections between the spheres. Note that this means that finding how many $$n$$-letter words are there in a neighbourhood of a given radius around a point is going to be important because we have to ensure that none of these is part of the code that we are going to use.

In the rest of this post, we will be concerned with only zero-error information theory, the second error criteria used above. In this case, we know a lot for the Hamming metric - given a particular rate, we know that a particular rate is achievable (that is, we can construct a code that achieves that rate), and we know that some rates are not achievable. The achievability result is via the Gilbert-Varshamov bound, while there are several upper bounds known (like the Hamming, singleton and Elias-Bassalygo bounds). Unfortunately, these do not match, and a gap exists [^2] which has been an open problem for quite some time now. 

<figure>
  <img src='/assets/images/bounds.svg' width="100%" alt='Binary Hamming metric'/><br>
  <div class="divider"></div>
  <figcaption> What the bounds look like for the Hamming metric. The Gilbert-Varshamov bound is the achievability result. The rest are upper bounds. Note the gap between them. </figcaption>
  <div class="divider"></div>
</figure>

In the case of the Lee metric, far less is known. We saw above why it is important to bound the number of words that are within a given distance away from a point, a quantity that we will call the size of a ball in the metric. The main difficulty in the case of the Lee metric is that it is much harder to find the size of a ball in the Lee metric than it is in the Hamming metric. Assuming we know the size of the ball in the Lee metric, a formula for each of the rate-distance bounds mentioned above appears in a wonderful book - *Algebraic Coding Theory* by Elwyn Berlekamp.

So now, the issue is to figure out what the size of a ball in the Lee metric is. This is the main content of our paper. Once we had this result, we were able to use Berlekamp's work to immediately obtain the above-mentioned bounds for the Lee metric.

# Our approach

## First steps

The first step was essentially a rediscovery of results that were known when Berlekamp wrote his book in the 60s. The idea is that one can think of this problem as estimating a particular coefficient in the expansion of a particular generating polynomial for the metric. To gain some intuition for this, consider the simple case of the binary Hamming metric, and suppose we need to find all the $$n$$-letter words that are a Hamming distance $$d$$ away from the word $$(0, \ldots, 0)$$[^3]. The Hamming metric just says that if there are $$d$$ locations where two equal length words differ, the Hamming distance is $$d$$. The required number of words is given by the number of choices of $$d$$ positions out of $$n$$ that will have $$1$$'s, which is simply $$\binom{n}{d}$$. This is also the coefficient of $$x^d$$ in the polynomial $$(1+x)^d$$. One simple way to understand the equivalence is that this coefficient also involves the choice of $$d$$ $$1$$'s from $$n$$ choices. 

This idea generalises to the Lee metric. Say the alphabet size in the Lee metric is $$5$$. Then the generating polynomial is given by $$(1 + 2x + 2x^2)$$, and the problem of finding the size of the Lee ball of radius $$d$$ reduces to finding the coefficient of $$x^d$$ in $$(1 + 2x + 2x^2)^n$$. Now, this is not an especially easy problem, because no such simple idea as the one in the case of the Hamming metric works in this case. There exist formulae for this (also known from the 60s), but they are a) difficult to use and b) do not give much insight to the problem. I was at this time doing an online course on analytic combinatorics on Coursera, and there they talked about problems of this form and how to find analytic solutions for the same. I learned a lot of interesting new approaches to solving problems like this (in fact the first time I thought about the generating polynomial method of solving the problem was while doing the course), but ultimately in turned out that the techniques in the course weren't well suited for this particular application (in particular because here we need to fix $$n$$ to be a particular finite value and there one could take the limit as $$n \rightarrow \infty$$, and the forms of the polynomials that we were working with could not be handled very easily via the techniques proposed in the course). 

## A question
While spending a few weeks trying to use techniques from analytic combinatorics and ruling them out one by one, I noticed that even the Hamming metric calculations are done using assuming that we are finding the coefficient of some $$x^d$$ where $$d$$ is then the location of the largest coefficient. I figured it would be a start if we could at least figure out where the maximum coefficient would be, we would at least know the parameter range where we would be working. After a few days wrestling with this problem, I seemed to have guessed a solution to it but was not able to prove it myself. So I posted the following question on the Mathematics StackExchange - [Largest coefficient in the power of a polynomial](https://math.stackexchange.com/questions/3057144/largest-coefficient-in-the-power-of-a-polynomial). A couple of answers could be used to get a proof of the maximum coefficient, and I finally hit upon *some* path of progress - I could use the central limit theorem to find the required coefficients for large enough $$n$$. Using Python's `numpy.polynomial`, I was able to get some graphs that showed me how the coefficients were behaving and how the normal approximation looked. I tried to use the results to obtain the bounds that we want, but the results were rather bad - they didn't even match the known results for the Hamming case, leave alone the Lee metric. When I went to see what the problem was, it was quite apparent - I had been using the log scale to look at the graphs, and the normal approximation was really good close to the peak but was really bad away from it. The log scale hid the fact that a couple of standard deviations away from the peak, the approximation was giving a value many orders of magnitude more than the actual value (say $$10^{10}$$ times higher). 

## Large Deviations and Sanov's theorem

This was a problem that reeks of large deviation theory - but it took me some time to recognise that because I had not used it before. Large deviation theory, as the name says, gives good bounds when one is working more than a few standard deviations away from the central peak. 

One of the basic results in large deviation theory is something called Sanov's theorem. It gives a powerful bound on the size of a set of type classes drawn from a probability distribution. The idea is as follows - suppose we have a discrete probability distribution, like the one that governs what face of a die comes up when it is thrown. Now, if we sample the probability distribution $$n$$ times (throw the die $$n$$ times), the outcomes will probably not be distributed exactly like the underlying distribution, but would be something called the empirical distribution - in the case of a die, this would consist of the number of times each number came up when the die was thrown $$100$$ times. Empirical distributions are also called types, a powerful concept in information theory, with several very nice properties. A type class is the set of all outcomes which have the same type [^4]. Now, given a set of types, Sanov's theorem allows us to bound the size of that set of types - the number of sequences such that their type is in the set. In our case, the class is just the set of all types such that the expected value with that probability distribution is less than $$d/n$$. This could be calculated using the normal approximation, but as mentioned earlier, the bounds obtained from it are pretty poor away from the peak.

## Convex Optimisation

Sanov's theorem requires us to find the type in the set that has the minimum relative entropy with the underlying probability distribution. This is a convex optimisation problem, and one could take its dual. The dual problem was just a complicated single variable optimisation that became something that I could handle without any of the sophisticated methods used to solve convex optimisation problems, using some Python code that ran reasonably quickly. This was part of the problem solved - numerically finding this maximising parameter gave some upper bound on the required coefficient. I wanted something better.

## A weird function

By the duality properties of convex optimisation it was clear that any positive value of the single parameter that the dual was over would work, so what remained was to choose what the positive value would be as a function of the expected value that was used to define the type class. I plotted out what the optimal value looked like, and it seemed an odd kind of curve. Now the first thing that entered my head was that the negative of the curve looked like a $$q$$-th root function, appropriately scaled and shifted. Now, using `curve_fit` from `scipy.optimize` in Python, I was able to fit it to other functions, like polynomials or exponentials, but either they were very sensitive to parameters or were not very good fits - something that can be quantified using the output of the `curve_fit` function. Anyway, it turned out that the best fit among all the functions I tested was indeed given by that weird function, and that's what found its way into the paper. We also found that perturbing the optimal values for the constants in this fit did not affect the final result much - so this fit was robust in some sense. If you look at the curve and some other functional form comes to your mind, I would love to know it!

# Final thoughts

Once we obtained the formula for the size of the Lee ball, all that remained to do was to substitute the result in the formulae from Berlekamp's book and plot the results. The results for $$q = 6$$ are shown below. We also verified that $$q = 2$$ with our method gives the same results as the binary Hamming case pointed out above - one way in which we were able to be somewhat sure that the method works. 

<figure>
  <img src='/assets/images/Leebounds.svg' width="100%" alt='Lee metric for q=6'/><br>
  <div class="divider"></div>
  <figcaption> What the bounds look like for the Lee metric with alphabet size of \(6\). Note a few similarities with the Hamming case. The GV and EB bounds agree on where the rate is zero (\(\delta = 1.5\)). There is again a gap between the upper and lower bounds, and the EB is again the tightest upper bound.</figcaption>
  <div class="divider"></div>
</figure>

<figure>
  <img src='/assets/images/comparisonbounds.svg' width="100%" alt='Comparison with the Hamming case'/><br>
  <div class="divider"></div>
  <figcaption> Our technique (markers) compared with the known results for the Hamming metric case (lines). </figcaption>
  <div class="divider"></div>
</figure>

If you are wondering what we used to make the graphs, there's a very nice way of using Latex in `matplotlib` in Python, and `matplotlib` can also be made to output the graphs in SVG, for the rather good looking graphs that you see both in this post and the paper.

If you are interested in looking at out code, it is all reasonably well documented and [uploaded on Github](https://github.com/sagnikb/LeeMetric). If you have any thoughts about this work, use the comment section below or get in touch via email. Provided things work out, I might be presenting this at [ISIT 2019](https://2019.ieee-isit.org/), so this might not be the last time that this paper is featured on this blog.

***

[^1]: Brief side note here. One might wonder about the metric that describes the situation where 'closeness' is defined by arranging on a line and not a circle. In this case, it can be shown that there are no channels that are matched to this metric, and so, even though the metric is mathematically interesting. it doesn't concern us that much here (it's not just mathematically interesting, but a situation where it would be of interest to an information/communication theorist would be too big a detour for this blog post.)

[^2]: In the Hamming case the gap exists for alphabet sizes less than $$49$$, above which there is a construction based on algebraic geometry that closes the gap.

[^3]: Point to note - for 'nice' metrics, one can always translate in this way to calculate the size of the neighbourhood around zero.

[^4]: One of the cool properties of types is that all members of the type class have the same probability. 