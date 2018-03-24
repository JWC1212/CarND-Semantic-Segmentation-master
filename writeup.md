**Path  Planning Project**

The goals / steps of this project are the following:

* Label the pixels of a road in images using a Fully Convolutional Network (FCN).

---

#  Selected model
## A variation of VGG16 is selected as pre-trained model. I added a 1x1 convolution layer to layer 7's output of this model to get a 1x1xnum_classes output which is also input for up-sampling. The whole model is so called FCN-8s.

#  Up-sampling
## Last convolution layer's output is up-sampled with kernel size 4 and stride 2.
## This up-sampled output is again combined with pooling-4 layer's output.
## This combination result is again combined with pooling-3 layer's output.
## This result is up-sampled with kernel size 16 and stride 8 to get the same size as original image's
## Both conv2d and conv2d_transpose layers use kernel regularization and random kernel initializer

#  Hyperparameter and optimizer
## Epoch equals to 30
## Batch size equals to 2
## Learning-rate 0.0001
## Optimizer is AdamOptimizer
## loss consists of cross entropy loss and regularization items from convent and transpose convnet

# Metrics
## Mean IoU:not used
## Loss:decreasing over time




