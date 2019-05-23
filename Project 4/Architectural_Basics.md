# **Architectural Basics** #

## 1. 3x3 Convolutions
3x3 convolutions are building block for a DNN. We can use 3x3 kernels to acheive the receptive field of 5x5, 7x7 ....   
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
How many layers depends on the size of the objects in the images.
## 5. How do we know our network is not going well, comparatively, very early
## 6. MaxPooling
## 7. Position of MaxPooling
## 8. The distance of MaxPooling from Prediction
## 9. 1x1 Convolutions
## 10. Concept of Transition Layers
## 11. Position of Transition Layer
## 12. SoftMax
## 13. Dense Layers or FC Layers
## 14. When do we stop convolutions and go ahead with a larger kernel or some other alternative (which we have not yet covered)
## 14.5 Over fitting
## 15. Image Normalization
## 16. Batch Normalization
## 17. The distance of Batch Normalization from Prediction
## 18. DropOut
## 19. When do we introduce DropOut, or when do we know we have some overfitting
## 20. Batch Size, and effects of batch size
## 21. Number of Epochs and when to increase them
## 22. When to add validation checks
## 23. Learning Rate
## 24. LR schedule and concept behind it
## 25. Adam vs SGD
## 26. Forward pass, the loss function, the backward pass, and the weight update

