---
layout: single
title: "Shannon's Channel Coding Theorem"
date: 2018-07-27 14:00:00 +0530
excerpt: The (highly) non-trivial content of Shannon's Channel Coding theorem
tags: coding-theory information-theory
categories: academic
comments: true
header:
  teaser: '/assets/images/shannon-teaser.svg'
---

Let me start with some quick praise of MIT and its educational outreach programs, mainly via [MIT-OCW](https://ocw.mit.edu/index.htm) and MITx courses on [edX](https://www.edx.org/). These have been an integral part of my college life and as noted [here](/blogposts/Why-quantum), are one of the reasons I am studying the things that I do. [^1]  

Coming to the point - I was going through a course on Quantum Error Correction, Complexity and Fault Tolerance offered by MIT on edX. Even though I wasn't able to complete it on time because I discovered it very late, I learned a lot from that course, one of which I will talk about in this post. 

So Prof Isaac Chuang wanted to quickly explain the point of Shannon's Channel Coding theorem in order to draw connections with von Neumann's pioneering observations in fault tolerant computing, and he came up with an interesting way to put it that I hadn't explicitly thought about before.

A quick description of the setting of the channel coding problem: suppose Alice and Bob are trying to talk to eachother and they have to do so over a noisy channel (which may simply be the air from Alice's mouth to Bob's ear in a noisy marketplace). Somehow, Alice and Bob must ensure that they are able to communicate with low rate of error even over such a channel. Shannon's channel coding theorem tells us something non-trivial about the rates at which it is possible to communicate and the probability of error involved, but to understand why it is so cool let's spend some time imagining that we don't know what Shannon's result is and think about what we might intuitively expect to happen. 

Imagine a professor lecturing in a noisy classroom. We might expect that if he speaks faster and faster, then it will become more and more difficult to understand what he's saying, that is, the probability of error will increase. He might need to repeat what he said, but that would only reduce the rate. Therefore, it is reasonable to expect that as the rate increases, the communication becomes more and more error-prone. If we plot the probability of error versus the rate of speaking, intuitively we might expect to see something like this...

<figure>
  <img src='https://lh3.googleusercontent.com/NhANZjrNhLam1Sz4DaGCtKQVTOsJg5KCB_JI47W0RU_ECyYF99csfK2R0P82f1rGlmZ2MikhUJLYT6U5vjQZf1d_RjmefLnpc3v5fyPwxWMOfitteGD_QrTXO2yqfvx1X6aTEh2Y-NY=w2400' width="70%" alt='Intuition says...'/><br>
</figure>

However, Shannon showed that this is not the case. His result basically showed that there is a rate C, called the capacity, associated with a channel which precisely characterises what rates are possible and what are not. Every rate below C can be achieved with negligible probability of error (in the limit of large block-lengths, a subtlety that, along with several others, I will ignore to make in order to illustrate the point here) and every rate higher than C will result in error probability bounded away from zero (that is, always greater than some number which is greater than zero). In fact, it was shown later that when the rate is higher than C, the probability is actually very close to one, and if we re-draw the graph, we get something like this...

<figure>
  <img src='https://lh3.googleusercontent.com/2RJYbUwSOYv2_yUYnaNxmyQt6ZiFYQMoLn9bY1DzFPzKkwLN3WvN6PxeXb2ON8WoaS-4vHTw0RaFVmP_x6Yko55HCpIsD8f9yvljW1676NphcTI_MtBfEejRO2-iXgDXEUdRdpaJLgM=w2400' width="70%" alt='Intuition says...'/><br>
</figure>


This is precisely the non-intuitive content of Shannon's channel coding theorem. A similar result was derived by von Neumann where he showed that as long as the basic gates used in constructing a computer are more reliable than a certain threshold, one could make a highly precise computer. What prompted him to think in this direction and why that result is hugely important today is an interesting tale in its own right, and one that I won't be attempting here. 

The impact of Shannon's results can hardly be overstated - one could argue that his highly original ideas ultimately kickstarted the communication revolution that has ended up giving us mobile phones, the Internet etc. This way of looking at it gives us a way to appreciate Shannon's result without going into any math whatsoever.

[^1]: Quick side note: that link is a bit backdated at this point. Information and coding theory have gained a good amount of real estate since then as far as my interests are concerned, but that is another story for another day. 