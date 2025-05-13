# Bootcamp of Deep Learning Models
## History of AI Summary
## Perceptron
## Deep Neural Networks (DNN)
### DNN for Classification
### DNN for Regression
### Optimizers
```python
from tensorflow.keras.optimizers import Adam
adam_opt = Adam(learning_rate=LEARNING_RATE, beta_1=0.9, beta_2=0.999, epsilon=1e-8)
model.compile(optimizer= adam_opt, loss="mean_squared_error", metrics=["mse"])
```
## GPU Access
- GPU usage in Google Colab
- GPU usage in Kaggle

## Kaggle
- Code Version Control in Kaggle
- Data Version Control in Kaggle

## Keras
### Sequential and Functional APIs in Keras
### Initializers
### Callbacks in Keras
- Model Checkpoint
- Learning Rate Scheduler
- Early Stopper
- TensorBoard
- Custom History

## How to Train a DNN
1. Proprocess Data: Data Normalization, Global variables
2. Weight Initialization
- Xavier/Glorot: sigmoid/tanh
- He: Relu
- Gaussian: samll $\sigma$
3. Choose activation function: Relu
4. Batch normalization: Especially for deep MLP later layers
5. Dropout: p dropout hyperparameter
6. Optimizer: Adam (Adaptive fast)
7. Hyperparameters
- Architectures: no. of layers, dropout rate, adam beta1&2
8. Loss function
- binary classification: log-loss
- k-class classification: multiclass log loss
- regression: squared loss
9. Monitor gradients: clipping
10. Monitor train-test curves
11. Avoid overfitting 

## Custom Dataset and Dataloader    
### Auto-Encoder
## Sequential Models
### Recurrent Neural Networks (RNN)
### Bidirectional RNN (Bi-RNN)
### Long Short Term Memory (LSTM)
### Gated Recurrent Unit(GRU)
## Feedback
[feedback link](https://futurepicx.com/feedback?id=DC7D9D1A-6BFF-468F-87E3-A5997A4DCB6E)