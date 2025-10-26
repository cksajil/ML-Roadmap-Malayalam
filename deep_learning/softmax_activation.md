# Softmax Activation Function
Softmax activation function is commonly used in the output layer of classifier neural network. We know what is a classifier algorithm is. 

An algorithm which can tell whether a person is wearing mask or not is a classifier. Classifiers can be binary classifier or multiclass classifiers. A multi-class classifier example is recognizing digits in a vehicles number plates. At a given position it could be digits (0-9) or some letters (A-Z) possible.

## Why Softmax?

Such classifiers gives their prediction confidence in terms of probabilities. This is where softmax activation function comes in.

## Equation
$$\text{Softmax}(z_i) = \frac{e^{z_i}}{\sum_{j=1}^{K} e^{z_j}}$$