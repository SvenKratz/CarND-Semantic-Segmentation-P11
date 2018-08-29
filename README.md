# Semantic Segmentation Project
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

This repository contains my solution to the Udacity Self-Driving Car NanoDegree Semantic Segmentaton Project

This repository contains the following notable files:

* `main.py` : Implementation of the semantic segmentation fully convolutional model/
* `./runs/` folder: stores output of model runs on image data. Parts of the image segmented as "road" are highlighted in green.
* `Semantic Segmentation.ipynb` : Contains both main and helper in a Jupyter notebook (used for development).

## Instruction for running

* ensure Tensorflow with GPU support is available on your machine
* run `python main.py`

## Comments on the Fully Convolutional Model Implementation

As per the project instructions, the fully convolutional model was a adapted from the [Long et al. paper](https://www.cv-foundation.org/openaccess/content_cvpr_2015/papers/Long_Fully_Convolutional_Networks_2015_CVPR_paper.pdf).

Here is a graphical depiction of the model architecture:

![model_architecture](./model_architecture.png)

The model layers are initialized with a truncated normal initializer (sigma=0.01) and use an l2 regularizer.

I used an Adam optimizer to minimize the cost function.

I experimented with different learning rates, epoch numbers and hidden layer keep probability and found the following hyperparameters to work well:

* learning rate: 0.001
* number of epochs: 150
* keep probability: 0.75

I kept track of the average loss rate by outputting it at the end of every epoch, and verified that is gets monotonically lower, which means that the optimizer is converging.

## Output Examples

Here are some semantic segmentation output examples:

![example 1](./runs/1535510393.7355092/um_00019.png)

![example 2](./runs/1535510393.7355092/uu_000085.png)
