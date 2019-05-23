# **Architectural Basics** #

## 1. 3x3 Convolutions
3x3 convolutions are building blocks for a DNN. We can use 3x3 kernels to acheive the receptive field of 5x5, 7x7 ....   
They were first used in the VGG model. Today all the DNN are using 3x3 kernels
## 2. Receptive Field
Receptive field of a layer is the logical area of the input image (at 1st layer) on which kernel of that layer is convolving. For example -   

| Input Image Dimensions | Kernel Dimensions | Receptive field |
| ---------------------- | ----------------- | ---------------- |
| 28x28x1 | 3x3x1x10 | 3x3 |
| 26x26x10 | 3x3x10x20 | 5x5 |
| 24x24x20 | 3x3x20x30 | 7x7 |
| 22x22x30 | 3x3x30x40 | 9x9 |
And so on ....

## 3. Kernels and how do we decide the number of kernels?
Kernel is basically a feature extractor. Kernels are randomly initialized and trained by backward propagation to extract the right features so that model can predict with highest acuuracy.    
Number of kernels depends on the expressivity expected from the NN which in turn depends on the inter and intra-class variations in the features of the images.
## 4. How many layers
How many layers depends on the size of the objects in the images. We will add as many layers such that the receptive field of the final layers is approximately equal to the size of the objects. Here the assumption is that size of all the objects is approximately same.
## 5. How do we know our network is not going well, comparatively, very early
If the validation accuracy is not improving much in the fist few epochs then something is wrong with the network.
## 6. MaxPooling
Maxpooling is a technique of convolving a 2x2 matrix with a stride of 2. The largest of the 4 numbers repalaces them. Maxpooling helps us achieve accuracy in cases of small object rotation.
## 7. Position of MaxPooling
Positon of Maxpooling depends on the size of images, we can place maxpooling layer where the receptive field of the previous layer seems to have edges and gradients in it.
## 8. The distance of MaxPooling from Prediction
Maxpooling should be atleast 3-4 layers away from the prediction layer. Applying maxpool just before the prediction layer turns imanges into some kind of blob.
## 9. 1x1 Convolutions
1x1 Convolutions are used to decrease the number of channels in the transition block. The way 1x1 convolutions works is by combining the multiple channels into a single one.
## 10. Concept of Transition Block
Transition block consists of maxpool and 1x1 convolution layers. The purpose of transition block is to reduce the with and depth of the channels and to achieve some kind of consolidation of important features before diversifying again.
## 11. Position of Transition Block
Transition blocks are placed in between the convolution blocks to achieve consolitions.
## 12. SoftMax
Softmax is an algorithm in the output block to achive better probablity-like outcomes of various classes. Softmax does not tell the actual probablity. We should never use softmax in the models which predict medical diseases or wherever the prediction have serious and life impacting outcomes.
## 13. Dense Layers or FC Layers
Dense layers are not used in DNN's anymore. Dense layers are layers where each output in the layer is connected to all the inputs from previous layer.
## 14. When do we stop convolutions and go ahead with a larger kernel or some other alternative (which we have not yet covered)
When the receptive field of the layer is nearly equal to the object size in the image(assuming there is only single object as in MNIST). Now we go ahead and go ahead with the larger kernel which is of the same dimensions as the image size. Instead of this we will use *Global average pooling* in future.
## 14.5 Over fitting
Overfitting is achieved when there is a difference between the testing accuracy and validation accuracy. Here the validation acuuracy is not reaching the value what we expect it to achieve.
## 15. Image Normalization
Image normalization is normalizing the pixel values of the input image. Here we divide the each pixel value by largest number so that each pixel value in the image matix will become range bound.
## 16. Batch Normalization
Batch normalization is logically same as image normalization. But here we apply normalization in between two layers of the model so that neurons in each channel will be range bound and all the feature will have the same voice before moving ahead.
## 17. The distance of Batch Normalization from Prediction
We do last batch normalization after the final 1x1. This will basically be part of global average pooling(to be learbed later).
## 18. DropOut
Drop out is the concept of dropping out few kernels in a single layer during training. We apply dropout of less that 0.15 at each layer. This helps NN to achieve higher redundancy and learn new ways to predict the class. After dropout the testing accuracy will be less then the validation accuracy.
## 19. When do we introduce DropOut, or when do we know we have some overfitting
When the validation accuracy is less then the testing accuracy.
## 20. Batch Size, and effects of batch size

## 21. Number of Epochs and when to increase them
## 22. When to add validation checks
## 23. Learning Rate
## 24. LR schedule and concept behind it
## 25. Adam vs SGD
## 26. Forward pass, the loss function, the backward pass, and the weight update

