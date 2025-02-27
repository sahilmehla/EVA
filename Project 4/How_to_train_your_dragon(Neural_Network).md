# **How to train your Dragon!!! (Neural Network)**
### 1. Fix the architecture of the NN, by fixing the number of layers in the convolutional(Increase channels) and transition block(decrease the channel dimensions/maxpool and the number of channels/1x1). The number of hidden layers in the first convolution block depends on the size of the object and the receptive field at which we will be able to capture the edges/gradients so that transition(maxpool) would be effective.
### 2. Train with max number of parameters, for example use 32 -> 64 -> 128 -> 256 -> 512 etc. and observe the results and accuracy.
### 3. Train with the minimum number of parameters and observe the results and accuracy.
### 4. Add batch normalization after each layer, but not after the transition block. The batch normalization which is done in the output block is called *"Global average pooling"*.
### 5. Increase the expressivity (no. of parameters) of the network to increase the accuracy (sometimes depends on the problem statement or the hardware limitations.
### 6. Add dropout(less than 0.15) after each convolutional layer but not in the transition block and output block. This will improve the acuracy of the network overall. Note that here the training accuracy will be less than the validation accuracy due to dropouts during training. Dropout provided more redundancy to the network. We will learn later that if we use *"Image Augmentation"* we might not need dropout.
### 7. Reduce the learning rate after each epoch to fine tune the accuracy further. The right approach that will be taught later is *"Reduce LR(learning rate) on plateu"*.
### 8. Finally play with number of parameters , batch normalization and dropout etc. that can be tried to train the network with minimum number of parameters acheiving the best accuracy.

## Points to remember
- Accuracy will increase with batch size to a certain point then it will start decreasing. The max batch size resulting in highest accuracy depends on the GPU capacity.
- For finding right intial learning rate for a image dataset, we have to use the learning rate finder.
- There is a tool called eNAS (Efficient Network architecture search) to get the best architecture to train on a dataset.
- Right now we are using sequential model. Yolo2 first introduced skip connections(funtional api) - To be learned later.
