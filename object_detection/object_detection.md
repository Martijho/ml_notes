#### Backbone architectures
Commonly used structures to use as backbone classifiers for object detection include MobileNet, ResNet, Inception and VGG

#### Learning Rate Warmup 
Learning rate warm up heuristic was introduced to overcome the negative effect of extremely large mini-batch size. 
Interestingly, even though mini-batch size used in typical object detection training is nowhere close to the scale in
image classification(e.g. 10k or 30k), a large amount of anchor size(up to 30k) is effectively contributing to batch
size implicitly. A gradual warmup heuristic is crucial to YOLOv3 (empirical observation)
Source: https://arxiv.org/pdf/1902.04103.pdf

#### Mixup for Object Detection
Training with mixup for object detection increases robustness towards object in unexpected scenarios (i.e: "elephant in 
the room"). Alpha blending the input images with a alpha selected from a Beta(1.5, 1.5) distribution reportedly improves
mAP score for a YOLOv3 model on VOC from 81.5 to 83.54. Source: https://arxiv.org/pdf/1902.04103.pdf