---
title: "Research Proposal"
date: 2022-05-17T15:11:42-04:00
description: First draft of the research proposal
menu:
    sidebar:
        name: Research Proposal
        identifier: research-proposal
        parent: research
        weight: 250
draft: false
---

For my research, I'm planning to go into the area of predictive analytics, which is when historical data is used in order to
predict certain outcomes. In particular, I'm planning to use neural networks to do just that. It's not new that neural
networks have been used in predictive analytics, but the hurdle that hasn't been overcome yet is a set of hard and fast
rules to create the most optimal neural network. The best ways to do that are currently trial and error or intuition from
seasoned developers. The literature does have attempts to address this particular problem, such as Kavzoglu from 1999 and
Lafif Tej from 2018, both of them trying to find the optimal architecture of the neural network. However, the attempts are
only in one configuration of a neural network. I'll be trying to address all of the configurations of a neural network
through this research and come up with a thorough set of guidelines.

A neural network is an artificial intelligence structure containing neurons, or nodes. It's supposed to imitate a human
brain with regard to processing information. The neural network comprises multiple layers, which are what contain the nodes
themselves. To train the neural network, the nodes take in the numerical data, make calculations, and output the results
from those calculations and pass those results to the next layer. The numerical data should have two things: input variables
and the output variable. The input variables should have some correlation with the output variable in order to make good
predictions. Within the context of predictive analytics, the correlation of the data is crucial. The accuracy of the
predictions the neural network makes are reliant on the strength of the correlation of the data since the stronger the
correlation is, the less on average there is of a disparity between the predicted value and the actual value, therefore
increasing the accuracy of the predictions being made. The data has to be split into training data and test data so when the
neural network uses the training data, the test data is used to scrutinize the accuracy of the neural network's output after
the training is finished. There are three aspects of the calculations happening in a neural network: weight, bias, and
activation function. Each connection from one node to the next has a weight, which is a coefficient applied to the input
coming in to the node, and then a bias is added to that result. The bias is just a constant. After those two calculations
are done, then an activation function is used on that result. The output of that function is then passed to a node in the
next layer. This entire process, known as forward propagation, is repeated for all of the nodes in the neural network. After
the forward propagation, there needs to be a way to tune the neural network so that it closely resembles an output from the
test data. This is done through a process called backpropagation. There's plenty of multivariable calculus involved, and I
would have to brush up on that, but in short, it adjusts all of the weights in the neural network so that the calculated
output is as close to the test output as possible, which is done through a concept called optimization. There are plenty of
ways to perform optimization, but the most common way is through gradient descent. This cycle of forward propagation and
backpropagation is ideally done many times in order to adequately train a neural network.

There are a few configurations to be kept in mind when trying to construct and improve a neural network. One would
be the architecture. The architecture is essentially an overview of how many layers there are and how many nodes are in each
one. More configurations to be kept in mind is the activation function itself, regularization, regularization rate, and
learning rate. The learning rate is how much the weights are adjusted during the backpropagation process. Regularization is
a method of addressing the problem of overfitting, which is when the neural network is performing too well with predicting
the training data. That means that it can't reliably output anything else that relies on information outside of the training
data. There needs to be an adequate amount of randomness in the predictions in order for them to be good. When looking at
data, particularly plots, a common practice is to try to use linear regression, in this case, multiple linear regression, to
explain the relationship between variables. This would be done by using a linear regression line. In this case, there are
three explanatory variables that each have a coefficient. Regularization would shrink, or reduce those coefficients so that
there's a more stable fit and the predictions won't be as dependent on variables that may be less significant, reducing the
variance of the model. The variance is essentially the spread of data. Any linear regression line will have residuals, which
are just measures of how far data points are from the line itself. The line of best fit is usually determined by trying to
minimize the sum of the squared residuals by tweaking the slope and y-intercept values in the linear regression line. The
linear regression line with the lowest sum of the squared residuals is called the least squares regression line. To come up
with the least squares regression line, a calculator evaluates many sums of squared residuals while tweaking the slope and
y-intercept of the regression line. After those are evaluated, the minimum sum is found, and the slope and y-intercept used
to get that minimum sum will become part of the equation representing the least squares regression line. Regularization is
when a penalty is added to the sum of the squared residuals, and that gets minimized instead. This penalty is represented as
lambda times the absolute value of the slope for L1 regularization, or lasso regularization, and lambda times the square of
the slope for L2 regularization, or ridge regularization. Lambda in this case is just referred to as the severity of the
penalty, or regularization rate, which can be any positive number. To get the ridge regression line, plenty of lambda values
are evaluated, and through cross-validation, the one resulting in the least amount of variance in the model is selected,
along with the slope and y-intercept. Cross-validation is the splitting of the data set to training data and test data in
different ways. In ridge regularization, none of the input variables can be removed, while in lasso regularization, some of
the insignificant input variables can be removed. This is because when the regularization rate increases, in ridge
regression, the slope can never become zero, while with lasso regression, the slope can become zero, meaning that some of
the variables can have slopes of zero, effectively removing them from the equation. These choices regarding configurations
of the neural network are crucial for making a neural network optimal.

I created a neural network from scratch for my prototype. The prototype is meant to try to predict how many expected goals
from a certain hockey team there will be in the next game based on the Corsi percentage, Fenwick percentage, and shots on
goal from the previous game. The Corsi percentage can refer to many scenarios, but in this case, it is the percentage of
total shot attempts in a game by one team. The Fenwick percentage is the same thing, but excludes shots that were blocked. I
first need that particular data to feed the neural network with, so I downloaded a CSV from a hockey website which held all
of the information I needed to put into the neural network. With some primitive data wrangling, I managed to create a new
CSV that's appropriate for the neural network to use. This wrangling involved the use of R and the tidyverse library. First,
I had to filter the dataset so that only one entry represents one game. There were five entries for each game because there
were multiple situations for this game that were recorded as separate entries, such as even strength, power plays,
shorthanded, etc. Second, only the relevant columns were selected. The input for the neural network, which comprises the
Corsi percentage, Fenwick percentage, and shots on goal, was included.  Plus, the output for the neural network, which is
the expected goals, was included. This alone wasn't sufficient however because the percentages and the shots on goal are
only recorded after the game is played. For the neural network to have any prediction value, it would have to be based on
data that has already been recorded. That's why I proceeded to shift the percentages and shots on goal down by one so that
the entries would contain the data from the previous game. After that, the new CSV gets created. Once this new CSV gets fed
to the neural network and trained through the feed-forward propagation and backprogation process, the accuracy of the neural
network is evaluated. In this prototype, it's evaluated through the root mean square error (RMSE). If it's close to zero,
then it's pretty accurate, and if it's close to one, it's not. However, if it's too low, then the overfitting problem will
occur. Somewhere between 0.2 and 0.3 RMSE is ideal.

For the experiment, I tried to answer the question of whether the activation function played a huge role in the performance
of a neural network. The Python package used for the visualization was matplotlib. The experiment takes five activation
functions and individually apply them to the neural network, running it five times to get the RMSE each time. Higher order
functions were used in order to switch from one activation function to another. A bar chart is then displayed, showing the
RMSE of the neural network for each activation function. The results show that the activation function doesn't play a huge
role in neural network performance. Since the activation function is one of the configurations of neural networks, this
visualization of the experiment could help make more certain the degree to which this particular configuration has an impact
on the accuracy of the neural network. This experiment has flaws though, in that the design itself only has one arrangement
of data, and maybe the activation function could play a large role in another arrangement of data. Plus, in each execution
of the neural networks, the weights at the start of the execution are randomly generated. Therefore, there can't really be a
judgement of the difference in the performance of neural networks with different activation functions since the initial
weights are different in each execution. However, I think this experiment is adequate because the differences in randomly
generated weights isn't that significant in the grand scheme of things. At the end of the day, there could be an aggregate
of these executions for each activation function and the median would be accepted as the RMSE, but I didn't find much use in
consuming so much computing power or having such complexity for a primitive experiment like this.

This prototype was meant to be a start to the research project. With regard to the ethics of conducting predictive analytics
with neural networks, it primarily applies to where the data is coming from. If it's public data that anyone could access,
there isn't an ethical concern because theoretically, anyone could make those predictions using that data. If it's private
data, it's a different story because there is a disparity in access. Therefore, people will make better predictions than
others, and it would just be an uphill battle for people without access to the data. I'll try to use data that's already
available for anyone to use.

This research project is definitely feasible. It's just that a bevy of background knowledge needs to be accumulated before
embarking on this endeavor, such as calculus and linear algebra. The next steps would be to brush up on the math, do
research on existing neural networks, configurations, and justifications for those configurations, come up with the
guidelines, find a way to actually prove that the neural network is indeed optimal, and then create three presentable
neural networks based on the guidelines.