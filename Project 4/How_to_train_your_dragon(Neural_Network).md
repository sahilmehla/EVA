# **How to train your Dragon!!! (Neural Network)**
### 1. Fix the architecture of the NN, by fixing the number of layers in the convolutional(Increase channels) and transition block(decrease the channel dimentions/maxpool and the number of channels/1x1). The number of hidden layers in the first convolution block depends on the size of the object and the receptive field at which we will be able to capture the edges/gradients so that maxpool would be effective.
### 2. Train with max number of parameters, for example use 32 - 64 - 128 - 256 - 512 etc. and observe the results and accuracy.
### 3. Train with the minimum number of parameters and observe the results and accuracy.
### 4. Add batch normalization after each layer, but just once after the transition block.
### - 
