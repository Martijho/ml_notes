## Convolution

#### 1x1 Convolution
Convolution with a 1x1 kernel size can be viewed as "feature pooling". This is a
linear operation but is commonly used in conjunction with a non linear
activation function as ReLU.
  - This operation fills a role as dimensionality reduction if the output channel
  is larger than its input.
  - Combination of 1x1 (x F) convolution is mathematically equivalent to a
  multi-layer perceptron.


#### Distributed Convolutional Kernels
The kernel size is proportional with the computational cost of the convolutional
operation, meaning a 7x7 kernel size have a computational cost 5.4 times that of
a 3x3 kernel.
  - Inception-v2 replaced the 7x7 kernel sizes in v1 with 3 consecutive 3x3
  convolutions where the first had output channels of 32 and a stride of 2,
  while the last had an 64 output channels
  - While replacing a 3x3 kernel with 1x3 + 3x1 convolutions reduce the number
  of parameters, the ability to perform diagonal filtering is lost. Some report
  of increased computational time also. (why is diagonal filtering lost?!)
