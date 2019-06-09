# Comparison of Various Activation Functions in Artificial Neural Network 
This project is intended to compare the performance of various activation functions in artificial nerual networks.

## What is an artificial nerual network?
Artificial nerual network is a software system that is modelled to replicate (but not necessarily identical) the learning structure of neurons in a biological brain. An aritifical nerual consists of multiple layers of nodes in which all the nodes of one layer is connected to the nodes of the next layer (see figure below).

![Image of ANN](https://icdn6.digitaltrends.com/image/artificial_neural_network_1-720x720.jpg)
>Image source: https://www.digitaltrends.com/cool-tech/what-is-an-artificial-neural-network/


A node or neuron is the most basic building block of a neural network, it takes in a set of inputs performs some calculations and produces on output. For further reading into the basics of nerual networks I have attached a link in the Appendix.

![Image of node](http://www.big-data.tips/wp-content/uploads/2016/06/perceptron-model.jpg)
>Image source: http://www.big-data.tips/neural-network

## Why are activation functions important and why do we need them?
Activation functions are used to introduce nonlinearity to artifical neural network which is requried to tackle complex realworld applications. For example, if we want our neural network to be able to identify objects in an image or video, translate text or speech from one language to another, etc. our
neural network should be able to learn non-linear states. 

## What are the different kinds of activation functions?

In this project, we are going to compare four of most popular activation functions, Sigmoid, tanH, ReLU and Leaky ReLU. 

### Sigmoid Function
![Image of sigmoid eq](/Images/sigmoid-function.PNG)
![Graph of sigmoid](https://cdn-images-1.medium.com/max/1200/1*Myto4ZQagAOoyom4tqkaRQ.png)
>Image source: Appendix [2]




The signmoid function was the one of the most frequently used activation. The sigmoid activation function can be used a good classifier because for a small x there will be a large y. This mean faster gradient decent. The biggest problem with this function is towards the ends of the function y does not react much with respect to a change in x. The derivative values in these regions are very small and converges to 0. This is called vanishing gradient. The means that the learning is going to be very slow these regions. Regardless, sigmoid is still used in the output layer while performing binary classifications.

In recent year there have been many other better alternatives that have been discovered such as tanH, ReLU and Leaky ReLU. 

### tanH Function
![Image of tanh eq](/Images/tanh.PNG)
![Graph of tanh](https://cdn-images-1.medium.com/max/1200/1*51Q7QouspCkOvENni2RwfQ.png)
>Image source: Appendix [2]

Hyperbolic tangent or tanh function has a very similar structure to the sigmoid function with the major difference being that the function is defined from (-1 to +1). This means that there is a more steep derivative as sigmoid. Therefore, this will be more efficient as it has a wider range for faster learning. 

Hyberbolic tangent function still has the major drawback that sigmoid function of vanishing gradient.


### ReLU Function
![Image of relu eq](/Images/relu.PNG)
![Graph of relu](https://cdn-images-1.medium.com/max/1200/1*m_0v2nY5upLmCU-0SuGZXg.png)
>Image source: Appendix [2]

ReLU is a recent invention which stands for Rectified Linear Units. The main advantages of using Relu as opposed to tanH and sigmoid is that it is much more computationally less expensive and it gets rid of the vanishing gradient issue. ReLU is mostly used in the hidden layers, it is almost never used in the output layer. The disadvantage with ReLU is that when x < 0 the gradient will be 0 which will result in the wieghts not being adjusted during decent. This results in the neuron to go into a state in which it stops responding to the variations in error/input. This is called dying ReLU problem.


### Leaky ReLU Function
![Image of relu eq](/Images/leaky-relu.PNG)
![Graph of relu](https://cdn-images-1.medium.com/max/1200/1*gDIUV3yonKbIWh_9Kl4ShQ.png)
>Image source: Appendix [2]

Leaky ReLU is a variant of ReLU which overcomes the dying ReLU problem. The difference between ReLU and Leaky ReLU is simply that instead of being 0 when x < 0; it is now a constant gradient α which is normally 0.01. This is still not used in the output layer as it still has some linearity as compared to sigmoid and tanh.









# Appendix
[1] Nerual Networks Basics: http://www.big-data.tips/neural-network
[2] Comparison of activation functions: https://towardsdatascience.com/comparison-of-activation-functions-for-deep-neural-networks-706ac4284c8a
