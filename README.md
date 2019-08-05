# DrugIt-Net


## 1) Three Channels Inputs
This is a 2D convolutional neural network architecture. 
The first layer consists of a fully connected layer, which inputs three channels of `molecular fingerprints`, `molecular descriptors`, and `2d molecular pharmacophores`. 
The second layer is convolution layer, but it is different from image processing in ResNet, the three channels are going to be done by reduce_max insteads of reduce_sum


## 2) FC layer is commit to learn the convolution matrix

