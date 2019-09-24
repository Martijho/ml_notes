#### Linear Scaling Learning rate by batch-size
In mini-batch SGD, gradient descending is a random process because the examples
are randomly selected in each batch. Increasing the batch
size does not change the expectation of the stochastic gradient but reduces its
variance. In other words, a large batch size reduces the noise in the gradient,
so we may increase the learning rate to make a larger progress along the
opposite of the gradient direction.
Goyal et al. reports that linearly increasing the learning rate with the
batch size works empirically for ResNet-50 training. In particular, if we follow
He et al. to choose 0.1 as the initial learning rate for batch size 256,
then when changing to a larger batch size b, we will increase the initial
learning rate to 0.1 × b/256.
source: https://arxiv.org/abs/1812.01187

#### Learning rate warmup
At the beginning of the training, all parameters are typically random values and
therefore far away from the final solution. Using a too large learning rate may
result in numerical instability. In the warmup heuristic, we use a small
learning rate at the beginning and then switch back to the initial learning rate
when the training process is stable. Goyal et al. proposes a gradual
warmup strategy that increases the learning rate from 0 to the initial learning
rate linearly. In other words, assume we will use the first m batches
(e.g. 5 data epochs) to warm up, and the initial learning rate is η, then at
batch i, 1 ≤ i ≤ m, we will set the learning rate to be iη/m.
source: https://arxiv.org/abs/1812.01187

#### Learning rate sweep
Finding an optimal learning rate can be done with a learning rate sweep.
Starting the learning rate with a low value (i.e: 10^-8) and increasing it every
training step, will sooner or later cause the loss to explode. Then plotting the
loss as a function of learning rate can point out areas where the learning is
optimal. Increasing the learning rate exponentially yields a plot with more fine
grained details in loss for lower learning rates.
Own experience:
  Using a LR-range found with a linear learning rate sweep on object detection
  problem with SSD-mobilenet. Training looks to be most effective when learning
  rate is around 10% of the found max-LR value.

#### Zero γ in ResNet-BatchNormalization blocks
A ResNet network consists of multiple residual blocks, each block consists of
several convolutional layers. Given input x, assume block(x) is the output for
the last layer in the block, this residual block then outputs x + block(x).
Note that the last layer of a block could be a batch normalization (BN) layer.
The BN layer first standardizes its input, denoted by xˆ, and then performs a
scale transformation γxˆ + β. Both γ and β are learnable parameters whose
elements are initialized to 1s and 0s, respectively. In the zero γ
initialization heuristic, we initialize γ = 0 for all BN layers that sit at the
end of a residual block. Therefore, all residual blocks just return their
inputs, mimics network that has less number of layers and is easier to train at
the initial stage.
source: https://arxiv.org/abs/1812.01187

#### Large batch size with distributed mini-batches
Layer-wise Adaptive Rate Scaling (LARS) offers layer-wise adaptive learning rate
and is reported to be effective for extremely large batch sizes (beyond 16K).
While in this paper we limit ourselves to methods that are sufficient for single
machine training, in which case a batch size no more than 2K often leads to good
system efficiency.
source: https://arxiv.org/pdf/1708.03888.pdf

#### Low-precision Training
Despite the performance benefit, a reducing floating point percision from FP32
to FP16 has a narrower range that makes results more likely to be out-ofrange
and then disturb the training progress. Micikevicius et al. proposes to store
all parameters and activations in FP16 and use FP16 to compute gradients. At the
same time, all parameters have an copy in FP32 for parameter updating.
In addition, multiplying a scalar to the loss to better align the range of the
gradient into FP16 is also a practical solution.
source: https://arxiv.org/pdf/1710.03740.pdf

#### Label smoothing
To avoid extreme "responses" by the trained model, where uncertainty is more
proportional to certainty, training against a ground truth scaled to be
1-ε for the true class and ε/(K-1) for the other where K is number of classes,
and ε is some constant
source: https://arxiv.org/abs/1812.01187

#### Mixup-training:
Given two image to train on (x and y), mixup-training produce two new image
which is a weighted interpolation between the two (i.e: xˆ = λx + (1 − λ)y),
where λ is drawn from a Beta(α, α) distribution.
This cause the network two be better with unexpected input scenarios.
source: https://arxiv.org/pdf/1710.09412.pdf

#### Learning rate schedulers
  - Cosine decay follows a cosine function that reduce the learning rate
  gradually every step towards 0.
  - Linear Cosine Decay follows a decaying cosine function similar to cosine decay. 
  source: https://arxiv.org/pdf/1709.07417.pdf 
  - Noisy Linear Decay is a Cosine Decay schedule with some added noise sampled from a 
  normal distribution N(\mu, \sigma) where \sigma follows a linear decay. 
source: https://arxiv.org/pdf/1710.09412.pdf

#### Stability training
Increasing stability in model output. Idealy, small differences in model input should cause
very similar outputs, but in some cases (e.g object detection) small fluctuations in input noise
can shift confidences above or below thresholds. Stability training is aimed at teaching the network
to produce the same output given two cases of the same input, with different sets of small
random noise added.
source: https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Zheng_Improving_the_Robustness_CVPR_2016_paper.pdf

#### Mean Teacher
source: https://github.com/CuriousAI/mean-teacher