## Eye grid

When performing object detection image is partitioned into smaller grids. To each grid is then performed same operation (eg. convolution or attention).

### Computer
![image](img/transformer.jpg) *Example of transformer partitions patches*

![image](img/convolution.jpg) *Example of CNN pipeline*


### Human
![image](img/eye.jpg)*Example of human partitioning in human eyes.*


## Description
This repo is an attempt to mimic human partitioning of input image. My hypothesis is that this method can substantially reduce number of dense convolutions in first layers of neural network.

First step is to apply blur like operation to image. This is form of input augmentation. Main purpose is to encode distance to point of interest.

Second step is then to apply some function to chunks of partially blurred image. Used function must be learnable, differentiable and same for all patches in image.

Third step is to try to predict output with respect to original image. Additionally center point of blurred image can move to get better representation of input.