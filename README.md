# XOR-problem


Introduction
This is the first in a series of posts exploring artificial neural network (ANN) implementations. The purpose of the article is to help the reader to gain an intuition of the basic concepts prior to moving on to the algorithmic implementations that will follow.

No prior knowledge is assumed, although, in the interests of brevity, not all of the terminology is explained in the article. Instead hyperlinks are provided to Wikipedia and other sources where additional reading may be required.

This is a big topic. ANNs have a wide variety of applications and can be used for supervised, unsupervised, semi-supervised and reinforcement learning. That’s before you get into problem-specific architectures within those categories. But we have to start somewhere, so in order to narrow the scope, we’ll begin with the application of ANNs to a simple problem.

## The XOr Problem
The XOr, or “exclusive or”, problem is a classic problem in ANN research. It is the problem of using a neural network to predict the outputs of XOr logic gates given two binary inputs. An XOr function should return a true value if the two inputs are not equal and a false value if they are equal. All possible inputs and predicted outputs are shown in figure 1.

<img scr="https://miro.medium.com/max/300/0*LYlt6CZJHOJkNRHJ.png"/>

XOr is a classification problem and one for which the expected outputs are known in advance. It is therefore appropriate to use a supervised learning approach.

On the surface, XOr appears to be a very simple problem, however, Minksy and Papert (1969) showed that this was a big problem for neural network architectures of the 1960s, known as perceptrons.

## Perceptrons
Like all ANNs, the perceptron is composed of a network of units, which are analagous to biological neurons. A unit can receive an input from other units. On doing so, it takes the sum of all values received and decides whether it is going to forward a signal on to other units to which it is connected. This is called activation. The activation function uses some means or other to reduce the sum of input values to a 1 or a 0 (or a value very close to a 1 or 0) in order to represent activation or lack thereof. Another form of unit, known as a bias unit, always activates, typically sending a hard coded 1 to all units to which it is connected.

Perceptrons include a single layer of input units — including one bias unit — and a single output unit (see figure 2). Here a bias unit is depicted by a dashed circle, while other units are shown as blue circles. There are two non-bias input units representing the two binary input values for XOr. Any number of input units can be included.

<img scr="https://miro.medium.com/max/445/0*wOYoifz24Wz_I152."/>

A simplified explanation of the forward propagation process is that the input values X1 and X2, along with the bias value of 1, are multiplied by their respective weights W0..W2, and parsed to the output unit. The output unit takes the sum of those values and employs an activation function — typically the Heavside step function — to convert the resulting value to a 0 or 1, thus classifying the input values as 0 or 1.
It is the setting of the weight variables that gives the network’s author control over the process of converting input values to an output value. It is the weights that determine where the classification line, the line that separates data points into classification groups, is drawn. If all data points on one side of a classification line are assigned the class of 0, all others are classified as 1.
