# Softmax Activation Function

Softmax activation function is a commonly used activation function in deep learning. In this tutorial, let us see what it is, why it is needed, and how it is used. Softmax activation function is commonly used in the output layer of classifier neural network. 

## What is a classifier?

Lets start with understanding what a classifier algorithm is. An algorithm which can tell whether a person is wearing mask or not is an example of a classifier. Also detecting alphanumeric characters in a vehiles number plate is also a classification task. At a given position it could be digits (0-9) or some letters (A-Z) possible.

Classifiers can be binary classifier or multiclass classifiers. The mask detection is a binary classification example and we can say recognising alpha numeric characters in a number plate is a multi-class classification example.

Such classifiers gives their prediction confidence in terms of probabilities. This is where softmax activation function comes in. A neural network classifier always predicts interms of prediction probability. It could be like if we give an person wearing mask, the algorithm may say I am 95% confidence that the person is wearing mask and 5% confidence that the person is not wearing mask. In some other scenarios where the algorithm is not sure about the prediction, it may say it is 55% wearing mask and 45% not wearing mask. The total sum will be corresponding to 1. This helps the algorithm to quantitatively represent how confident it is in a given prediction.

## But how does the neural network compute these probabilities?.

This is were softmax comes in

## Why Softmax?

At the output layer of binary classifier neural network it will be giving just two numbers. One representing the presense of mask and other representing for the absense of mask. To convert these into probabilites we can simply use softmax function.

## What happense in a softmax function?
In the softmax function the if the input is 2 numbers, the output will those two numbers transformed into their respective probability/fractional values. If the number of inputs in 4 the output will be 4 fractional numbers.

[4, 6] --> [0.119203, 0.880797] # in binary classification

[2, 2, 3, 4] --> [0.082595, 0.082595, 0.224515, 0.610296] # in four-class classifiction

The equation to convert these original numbers to their fractional/probability values as follows.


## How Softmax computes these values?
$$\text{Softmax}(z_i) = \frac{e^{z_i}}{\sum_{j=1}^{K} e^{z_j}}$$

## Equation Vs. Code Implimentaion

```python
import numpy as np

def softmax(x):
    return np.exp(x) / np.sum(np.exp(x))
```
Let us check by giving the above inputs and see if we get the same outputs. Also lets cross check if the total probabilities sum to 1.

## So why do we need such a complicated equation at all?. We can simply compute their percentage or fractional values?

To understand that lets try simple normalization

$$\text{Percentage}(z_i) = \frac{z_i}{\sum_{j=1}^{K} z_j}$$

Here there are mainly two problems:

- One reason is we want to handle negative numbers also. We cannot expect the output from output neurons be always positive

    #### Softmax 
    [-4, 6] --> [0.000045, 0.999955]

    #### Percentage normalization
    [-4, 6] ---> [-2, 3] # here we fail convert into convert proper fractions this way

- Another main reason is we want to bring non-linearity here. i.e. more emphasis should be given to higher numbers than lesser numbers. In the above example

    #### Softmax 
    [4, 6] --> [0.119203, 0.880797]

    #### Percentage normalization
    [4, 6] ---> [0.4, 0.6]
Softmax achieves this non-linearity with the help of exponential function in the equation

$$\text{Softmax}(z_i) = \frac{e^{z_i}}{\sum_{j=1}^{K} e^{z_j}}$$

If we take a look at the graph of exponential function, this makes sense.
![exponent](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c6/Exp.svg/1920px-Exp.svg.png)

For positive numbers the output gets higher as the number goes high. For negative numbers as input the output is mapped to a fractional value less than one but higher than zero. The higher the negative number the closer the output gets more and more close to zero.

The denominator in the equation makes sure the total probability sum to 1. So we can say the softmax function does the non-linear amplification in addition to the percentage normalization.

Hope this tutorial gave you 1000 foot view of what softmax function is and why it is designed the way it is. Happy learning :-).