# Comparison of Various Activation Functions in Artificial Neural Network 
This project is intended to compare the performance of various activation functions in artificial neural networks.

## What is an artificial Neural network?
Artificial neural network is a software system that is modelled to replicate (but not necessarily identical) the learning structure of neurons in a biological brain. Artificial neural consists of multiple layers of nodes in which all the nodes of one layer is connected to the nodes of the next layer (see figure below).

![Image of ANN](https://icdn6.digitaltrends.com/image/artificial_neural_network_1-720x720.jpg)
>Image source: https://www.digitaltrends.com/cool-tech/what-is-an-artificial-neural-network/


A node or neuron is the most basic building block of a neural network, it takes in a set of inputs performs some calculations and produces on output. For further reading into the basics of neural networks, I have attached a link in the Appendix.

![Image of node](http://www.big-data.tips/wp-content/uploads/2016/06/perceptron-model.jpg)
>Image source: http://www.big-data.tips/neural-network

## Why are activation functions important and why do we need them?
Activation functions are used to introduce nonlinearity to the artificial neural network which is required to tackle complex real-world applications. For example, if we want our neural network to be able to identify objects in an image or video, translate text or speech from one language to another, etc. our
neural network should be able to learn non-linear states. 

## What are the different kinds of activation functions?

In this project, we are going to compare four of the most popular activation functions, Sigmoid, tanH, ReLU and Leaky ReLU. 

### Sigmoid Function
![Image of sigmoid eq](/Images/sigmoid-function.PNG)
![Graph of sigmoid](https://cdn-images-1.medium.com/max/1200/1*Myto4ZQagAOoyom4tqkaRQ.png)
>Image source: [2]




The sigmoid function was one of the most frequently used activation functions. The sigmoid activation function can be used a good classifier because for a small x there will be a large y. This means faster gradient descent. The biggest problem with this function is towards the ends of the function y does not react much with respect to a change in x. The derivative values in these regions are very small and converge to 0. This is called vanishing gradient. The means that the learning is going to be very slow these regions. Regardless, sigmoid is still used in the output layer while performing binary classifications.

In recent year there have been many other better alternatives that have been discovered such as tanH, ReLU and Leaky ReLU. 

### tanH Function
![Image of tanh eq](/Images/tanh.PNG)
![Graph of tanh](https://cdn-images-1.medium.com/max/1200/1*51Q7QouspCkOvENni2RwfQ.png)
>Image source: [2]

Hyperbolic tangent or tanh function has a very similar structure to the sigmoid function with the major difference being that the function is defined from (-1 to +1). This means that there is a more steep derivative as sigmoid. Therefore, this will be more efficient as it has a wider range for faster learning. 

Hyperbolic tangent function still has the major drawback that sigmoid function of vanishing gradient.


### ReLU Function
![Image of relu eq](/Images/relu.PNG)
![Graph of relu](https://cdn-images-1.medium.com/max/1200/1*m_0v2nY5upLmCU-0SuGZXg.png)
>Image source: [2]

ReLU is a recent invention which stands for Rectified Linear Units. The main advantages of using Relu as opposed to tanH and sigmoid is that it is much more computationally less expensive and it gets rid of the vanishing gradient issue. ReLU is mostly used in the hidden layers, it is almost never used in the output layer. The disadvantage with ReLU is that when x < 0 the gradient will be 0 which will result in the weights not being adjusted during descent. This results in the neuron to go into a state in which it stops responding to the variations in error/input. This is called dying ReLU problem.


### Leaky ReLU Function
![Image of relu eq](/Images/leaky-relu.PNG)
![Graph of relu](https://cdn-images-1.medium.com/max/1200/1*gDIUV3yonKbIWh_9Kl4ShQ.png)
>Image source: [2]

Leaky ReLU is a variant of ReLU which overcomes the dying ReLU problem. The difference between ReLU and Leaky ReLU is simply that instead of being 0 when x < 0; it is now a constant gradient α which is normally 0.01. This is still not used in the output layer as it still has some linearity as compared to sigmoid and tanh.



### Set Up
To ensure that the machine running the ipython notebooks are set up correctly, follow these steps prior to running the codes:
* Install python3 and pip

```
sudo apt-get install python3-pip
```
* Install git, to pull this repository

```
sudo apt-get install git
```
* Pull the GitHub repository

```
git clone https://github.com/soorajvk/activation-function-comparison.git
```
* Navigate into the folder and run the requirements.txt
```
cd activation-function-comparison
pip install -r requirements.txt
```
* After the installations are over, run jupyter notebook and replace `<filename>` with the filename of the notebook
```
jupyter notebook <filename>.ipynb
```
### Conclusion
The conclusions listed here were drawn from running the test scenario defined in the notebooks in this repository. The test scenarios were build using tensorflow backend and keras higher level APIs. 

#### Sigmoid

![Image of sigmoid output](/Images/sigmoid-output.png)

Using sigmoid was found to have the lowest accuracy after training at around 70%. This is would have been worse if the predicted output during training was highly skewed to left or right where the gradient is close to zero. Therefore, sigmoid generally has a slow learning rate (not the hyperparameter) and is generally never used.

#### tanh

![Image of tanh output](/Images/tanh-output.png)

Using tanh outperformed the sigmoid function by a big margin with an accuracy of 87.4%. This is due to the fact that tanh has a larger gradient in the centre as compared to sigmoid. This would have still had the same drawback as the sigmoid when it comes to having a highly skewed predicted output during training.

#### ReLU

![Image of tanh output](/Images/ReLU-output.png)

Using ReLU during training exhibited the highest learning by achieving an accuracy of 94%. One of the main reason for using ReLU is because of this fast learning during training and it is less computationally heavy as sigmoid and tanh. ReLU still would be used in the output layer and still consists of a certain amount of linearity.


#### Leaky ReLU

![Image of leaky relu output](/Images/leakyrelu-output.png)

Using Leaky ReLU during training produced similar levels of accuracy (~93%) during training. Leaky ReLU is expected to show similar characteristics when the predicted output generated is positive but such factors are not possible to control during real-world application. Therefore, using Leaky ReLU will help full utilise the benefit of ReLU and minimizing its drawbacks.





# Reference
[1] Neural Networks Basics: http://www.big-data.tips/neural-network
[2] Comparison of activation functions: https://towardsdatascience.com/comparison-of-activation-functions-for-deep-neural-networks-706ac4284c8a
