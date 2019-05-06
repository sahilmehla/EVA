# Convolution

In mathematics the convolution is mathematical operation of two functions which results into a third function. Similarly in the context of image processing convolution is modifying each image pixel in a structured way. Lets take example of an image to understand it better.

![Vd-Orig.png](https://upload.wikimedia.org/wikipedia/commons/5/50/Vd-Orig.png)

Let imagine that its a 2-D(Grayscale) image i.e. the mathematical representation of this image is a 2-D array. 

2D image array will have numbers between 0 to 255, representing pixels. This array might look like -

```
	   [  0,   0,   0, ...,   0,   0,   0],
       [  2,   1,   2, ...,   0,   0,   0],
       [  0,   0,   0, ...,   0,   0,   0],
       ..., 
       [  0,   1,   0, ...,   4,  85,  96],
       [  0,   1,   0, ...,  54, 113, 115],
       [  0,   1,   0, ..., 121, 132, 145]
```

To perform a convolution on this image we will transform each and every pixel in the same way. 

Lets take a 2-D kernel/filter  -
$$
\begin{bmatrix}-1 & -1 & -1\\-1 & -8 & -1\\-1 & -1 & -1\end{bmatrix}
$$
How will this 2-D kernel convolve on the image array ?

We will take a 3x3 matrix from the top left corner of the image and multiply it with the 2-D kernel matrix and will add all the members of the resulting 3x3 matrix. This will be the result of this convolution. Similarly 

convolution will be performed on all the elements of the image array(where the element is center of selected 3x3 matrix). Convolution on the elements at extremities will be performed by padding the image array as required. Result of 3x3 convolution on the original image array will be an array of same size as the original image array. Image representation of the resulting array will be something like shown below -

![Vd-Edge3.png](https://upload.wikimedia.org/wikipedia/commons/6/6d/Vd-Edge3.png)

The 2-D kernel which is used above for convolution is a edge detection kernel. So we can see the resulting image highlighting all the edges of the original image.



**Reference for Images - https://en.wikipedia.org/wiki/Kernel_(image_processing)**



# Kernel/Filter

As illustrated in the previous example also, kernel is the basically the small matrix which convolves over the image under study and outputs a image highlighting the particular feature on the input image. Kernel/filer can be used to filter out various features of a images based on texture, edges, patterns.

_Each kernel when convolves on an input image produces its own output/channel._



# Batch Size / Epoch / Iterations

Lets consider a dataset of 1500 images. We cannot train our neural network for all the 1500 images at once.      So we will train let's say with 100 images at once so _100 is the **batch size**_. To train through all the images we need to train it 15 times, each time with 100 images. So __Iterations = 15 __ and as we training the neural network through entire image data set once so __epoch =1__.

_Epoch Definition_: Number of times the neural network is trained through the __ENTIRE__ dataset.



# 1x1 convolution(Network in Network)

![](https://raw.githubusercontent.com/iamaaditya/iamaaditya.github.io/master/images/conv_arithmetic/full_padding_no_strides_transposed_small.gif)

1x1 convolution is as shown above is nothing but simple multiplication of input(2D) elements to a 1x1 kernel to derive the output.  Similarly for 3D inputs 1x1 convolution will result in the addition of results of  multiplication of all corresponding elements.

The application of 1x1 convolution is often seen in shrinking the number of channels, where the number of channels in input are huge. Lets consider a 28x28x192 input, here the number of channels i.e. 192 are quite high to process. So to shrink the number of channels we use 32 1x1x198 kernel.



| Input     | Kernel (1x1) | Output   |
| --------- | ------------ | -------- |
| 28x28x192 | 1x1x198, 32  | 28x28x32 |

Resulting output is 28x28x32, the _channel size is reduced significantly from 192 to 32_.



# 3x3 Convolution



Lets consider and example to understand the 3x3 convolution. Following is the input(I), kernel(K) and output(O) matrix.
$$
\begin{bmatrix}1 & 2 & 3 & 4 & 5\\5 & 1 & 3 & 4 & 2\\4 & 2 & 3 & 1 & 5\\1 & 5 & 3 & 4 & 2\\1 & 4 & 3 & 2 & 5\end{bmatrix}
<=convolution=>
\begin{bmatrix}-1 & -2 & -1\\0 & 0 &0\\1 & 2 & 1\end{bmatrix}
=
\begin{bmatrix}3 & -3 & -6\\4 & 4 &0\\-11 & 3 & 2\end{bmatrix}
$$


Calculation of 1st element of the output is shown below :
$$
O[0,1] = (1*-1) + (2*-2) + (3*-1) + (5*0) + (1*0) + (3*0) + (4*1) + (2*2) + (3*1) = 3
$$
So the 3x3 convolution on a 5x5 matrix results into a 3x3 matrix and each element is calculated by adding the multiplication of corresponding elements. Similarly 7x7 matrix is convoluted to 5x5 after 3x3 convolution as show below.

![Convolution with Kernel of size 3x3](https://raw.githubusercontent.com/iamaaditya/iamaaditya.github.io/master/images/conv_arithmetic/full_padding_no_strides_transposed.gif)



# Feature Maps and Receptive Field



![img](https://cdn-images-1.medium.com/max/1000/1*ghaknijNGolaA3DpjvDxfQ@2x.png)

Above shown is a 5x5 input and a 3x3 Filter/Kernel. To perform convolution we slide the kernel over the 5x5 input and at every position we do element wise multiplication and sum the result. This sum goes into the **feature map** as shown below.

![img](https://cdn-images-1.medium.com/max/1000/1*VVvdh-BUKFh2pwDD0kPeRA@2x.gif)



The green area where the convolution occurs is **receptive field**. As the kernel is 3x3 so the receptive field is also 3x3. 

# FEATURE ENGINEERING

Feature engineering is the process to extracting features from data which act as input to the machine learning models. Good features help us further to improve the accuracy of the model.