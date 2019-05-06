#### Capsule Network
The capsule network consist of so called "capsules". This novel layer
architecture is designed to be scale, rotation and translation invariant, and
encodes its output as a 4D matrix, containing information about each prediction 
such as translation and rotation. 
The capsule design comes as a solution to the information loss that occur when using
a MaxPooling operation for increasing field of view between conv-layers. 
- [Paper](http://www.cs.toronto.edu/~fritz/absps/transauto6.pdf) 
- [Keras implementation](https://github.com/XifengGuo/CapsNet-Keras) 
- [Introduction blog post](https://medium.com/ai%C2%B3-theory-practice-business/understanding-hintons-capsule-networks-part-i-intuition-b4b559d1159b) 
- [Tutorial video](https://www.youtube.com/watch?v=pPN8d0E3900)
