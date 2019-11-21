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

#### Thoughts and theories

##### Training structure vs Inference structure
Training time is greatly benefitted by larger architectures as the increased capacity helps with generalization.
The performance of such larger models is not neccesarily reduced when transfering knowledge to a smaller architecture.
This might warrant a wholely seperate model design for training vs inference. E.g: A training structure might have the
same fundamental outline as the architecture designed for inference (memory/power/time constraints governs this domain),
but with a higher capacity through larger filters, residual connections and without bottlenecks. The greatest benefits
to the field of "ML in production" might therefore lay in smart architecture pruning.
* Could such pruning algorithms be reached with reinforcement learning?
    * Pros:
        * Simple rules can be applied to multiple cases.
        * Evaluation metrics are intuitive and obvious (though hard to execute in some cases)
    * Training is time consuming and might demand much from a training set

##### Object detection with non-rectangle object definition
Architectures dont see the actual defining bounding boxes in object detection.
When detection circular object for instance, an object could be defined by a circle and the coordinates would
therefore be 3 numbers (x, y for center and radius). Only difference to the detection algorithm would be seen in
loss calculation and evaluation. (or where ever detections are parsed in some way)

The predicted bounding box coordinates of an object could also be expanded to include a rotation. For person detection,
for instance, people leaning to one side will increase the box area to include a lot of background. Predicting a
rotation of the bounding box could take the place of predicting the 4 points in a slanting box, which is kind of
like polygon/keypoint detection.