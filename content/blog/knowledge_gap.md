---
title: "Knowledge Gap"
date: 2022-03-16T15:13:30-04:00
description: Trying to identify and fill the knowledge gap in the research
menu:
    sidebar:
        name: Knowledge Gap
        identifier: knowledge-gap
        parent: research
        weight: 250
draft: false
---

There are plenty of ways to create neural networks that conduct predictive analytics. Neural networks function by 
having an input layer, an output layer, and optional hidden layers in between. In a nutshell, these layers comprise
neurons that take in numbers as input and then, from a series of calculations, create output for the next layer to take
as input. Over time, these neural networks are trained with some algorithm, with the main goal of achieving the absolute 
minimum error. Essentially, the lower the error, the better performance the neural network has. There have been optimal 
neural networks for certain situations that were created, or ones claimed to be optimal, but in predictive analytics, 
there is an overall desire to have a generalized process where an optimal neural network could be created for a problem 
with historical data. This is the knowledge gap that I'll try to fill. Along with trying to find the best algorithm 
given a certain prediction problem, a crucial aspect of this process includes the architecture of the neural network. 
The architecture involves how many hidden layers there should be and how many neurons should be in each layer. In the 
coming months, I'll try to look at what other works have done when creating optimal neural networks, formulate a 
general process for creating them, and test that process out with a random prediction problem that has historical data.