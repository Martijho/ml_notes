# Machine Learning notes

### Table of contents
* <a href='network_architecture/network_architecture.md'>Architecture</a><br>
* <a href='neural_network_layers/neural_network_layers.md'>Network Layers</a><br>
    * <a href='neural_network_layers/neural_network_layers.md#1x1-convolution'> 1x1 Convolution </a><br>
    * <a href='neural_network_layers/neural_network_layers.md#distributed-convolutional-kernels'> Distributed Convolutional Kernels </a><br>
* <a href='network_training/network_training.md'>Network Training</a><br>
    * <a href='network_training/network_training.md#linear-scaling-learning-rate-by-batch-size'>Linear Scaling Learning rate by batch size</a><br>
    * <a href='network_training/network_training.md#learning-rate-warmup'>Learning Rate Warmup</a><br>
    * <a href='network_training/network_training.md#learning-rate-sweep'>Learning Rate Sweep</a><br>
    * <a href='network_training/network_training.md#zero-%CE%B3-in-resnet-batchnormalization-blocks'>Zero γ in ResNet-BatchNormalization Blocks</a><br>
    * <a href='network_training/network_training.md#large-batch-size-with-distributed-mini-batches'>Large batch size with distributed mini-batches</a><br>
    * <a href='network_training/network_training.md#low-precision-training'>Low-precision Training</a><br>
    * <a href='network_training/network_training.md#label-smoothing'>Label smoothing</a><br>
    * <a href='network_training/network_training.md#mixup-training'>Mixup Training</a><br>
    * <a href='network_training/network_training.md#learning-rate-schedulers'>Learning rate schedulers</a><br>
    * <a href='network_training/network_training.md#stability-training'>Stability training</a><br>
* <a href='object_detection/object_detection.md'>Object Detection</a><br>
    * <a href='object_detection/object_detection.md#backbone-architectures'>Backbone Architectures</a><br>
    * <a href='object_detection/object_detection.md#learning-rate-warmup'>Learning Rate Warmup</a><br>
    * <a href='object_detection/object_detection.md#mixup-for-object-detection'>Mixup for Object Detection</a><br>
    * <a href='object_detection/object_detection.md#foveabox'>FoveaBox</a><br>
* <a href='autoencoders/autoencoders.md'>Autoencoders</a><br>
    * <a href='autoencoders/autoencoders.md#variational-autoencoders'>Variational autoencoders</a><br>
* <a href='other/other.md'>Other</a><br>
    * <a href='other/other.md#capsule-network'>Capsule Network</a><br>
    * <a href='other/other.md#thoughts-and-theories'>Thoughts and theories</a><br>

#### Resources
* Books
    * [Elements of statistical learning](https://web.stanford.edu/~hastie/Papers/ESLII.pdf)
* Papers
    * [Bag of Tricks for Image Classification with Convolutional Neural Networks](https://arxiv.org/pdf/1812.01187.pdf)
    * [Bag of Freebies for Training Object Detection Neural Networks](https://arxiv.org/pdf/1902.04103.pdf)
    * [Recent Advances in Object Detection](https://arxiv.org/pdf/1809.03193.pdf)
* Web resources
    * [Articles and news](https://towardsdatascience.com/machine-learning/home)
    * [Database of papers and code examples](https://paperswithcode.com/sota)
    * [Yolo explained](https://medium.com/@jonathan_hui/real-time-object-detection-with-yolo-yolov2-28b1b93e2088)
* Datasets 
    * [VisualData](https://www.visualdata.io/)
    * [UCI](http://mlr.cs.umass.edu/ml/)
    * [Kaggle](https://www.kaggle.com/datasets)
    * [List of sets](https://www.datasetlist.com/)
    https://datasetsearch.research.google.com/
* Labeling tools:
    * [List of tools](https://www.datasetlist.com/tools/)
    * [Epigram tool](https://labeltool-web.firebaseapp.com/)
* Articles:
    * [Towards datascience](https://towardsdatascience.com/advanced-topics-in-neural-networks-f27fbcc638ae)
* Model conversion between frameworks
    * [Overview](https://awesomeopensource.com/project/ysh329/deep-learning-model-convertor)
* Debugging
    * ["Why is it not working"-checklist](https://blog.slavv.com/37-reasons-why-your-neural-network-is-not-working-4020854bd607)
* Guides
    * [Working with google spread sheet in python](https://towardsdatascience.com/accessing-google-spreadsheet-data-using-python-90a5bc214fd2)
        * [Gspread (more google sheet)](https://github.com/burnash/gspread)
