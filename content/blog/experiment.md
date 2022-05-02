---
title: "Experiment"
date: 2022-04-26T00:17:28-04:00
description: Overview of experiment
menu:
    sidebar:
        name: Experiment
        identifier: experiment
        parent: research
        weight: 250
draft: false
---

This experiment was meant to try to answer a question regarding a particular configuration of neural networks: the 
activation function. Is there a significant impact on the accuracy of the neural network based on what activation
function is used? The data set comprises hockey data from an individual team, the most relevant being Corsi percentage, 
Fenwick percentage, shots on goal, and expected goals. The Corsi percentage is just a percentage of the shots that one 
team has taken relative to all of the shots that were taken in a particular game. The Fenwick percentage is the same as
the Corsi percentage, but it just doesn't count the shots that were blocked or wide of the net. Expected goals in this 
context of hockey is a measure of the quality of chances that a team gets from their shots The neural network intends to
take the three input data points, those being the Corsi, Fenwick, and shots on goal from the previous game, and try to 
predict the expected goals for the next game. The root mean square error is used to evaluate the neural network. Five 
activation functions were used in the experiment, and the root mean square error was measured for five neural networks 
using each activation function. Essentially, the results say that the activation function itself doesn't really make a 
huge difference in accuracy. However, it could very much depend on the prediction scenario. Perhaps if there was a
non-linear correlation between data points, it would make a difference choosing one activation function over another. It
could also depend on the overall architecture of the neural network. That's what's left to be seen in later experiments.