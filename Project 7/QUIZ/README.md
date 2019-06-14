Open this LINK (Links to an external site.)Links to an external site. in your browser.
You are going to design a functional dnn
You are required to change the ## MAIN BLOCK in such a way that it represents this architecture:
x1 = Input
x2 = Conv(x1)
x3 = Conv(x1 + x2)
x4 = MaxPooling(x1 + x2 + x3)
x5 = Conv(x4)
x6 = Conv(x4 + x5)
x7 = Conv(x4 + x5 + x6)
x8 = MaxPooling(x5 + x6 + x7)
x9 = Conv(x8)
x10 = Conv (x8 + x9)
x11 = Conv (x8 + x9 + x10)
BIG KERNEL Operation (use a large kernel size (10 units), if required at this step to be able to add softmax in the next layer)
SoftMax
Directions:
Only 3x3 kernels (except in the 12th step above)
ReLU only
DropOut/BatchNormalization not needed (you can add if you want)
Don't change the batch size, epochs or optimizer in the default code
Do not change any other code. Each block is going to print current time for us to make sure that you are submitting the file with time around the same time you attempted this quiz
Finish running all the blocks
Make sure you have made the file public, so anyone with the link can view the file. 
Copy the shared link in the answer text box below (make sure no viewing permissions are required, to test open in an incognito window)
