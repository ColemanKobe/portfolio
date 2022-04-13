---
title: "Prototype"
date: 2022-04-12T09:40:13-04:00
description: 
menu:
    sidebar:
        name: Prototype
        identifier: prototype
        parent: research
        weight: 250
draft: false
---

One critical aspect of my research project is the building of a neural network from scratch. It hasn't been optimized 
with the best activation function or architecture yet; that will be what the whole research project will try to achieve.
My prototype is a neural network from scratch that tries to predict how many points a given hockey player will get in 
the next game. It takes in the season year, the ice time from the past game, the amount of shifts from the past game, 
and whether the next game will be an away or home game. The architecture is the following: three layers, the input,
hidden, and output layer. The input layer has four neurons, the hidden layer has two neurons, and the output layer has
one neuron. The activation function is a rectified linear unit. The mean squared error will be the overall evaluation of
the neural network. The results weren't great. A mean squared error of 0.75 means that it can't really capture all of
the data that was given and make reliable predictions. A few reasons could be the case. Perhaps the input data is
incorrect. In other words, I shouldn't use ice time and shifts from the previous game. Or perhaps the activation
function or the overall architecture is incorrect. Either way, the research will try to come up with the best
configurations for the neural network.