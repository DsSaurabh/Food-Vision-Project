# Food-Vision-Project
We're going to be build Food Vision project (a transfer Learning model), using all of the data from the Food101 dataset (75,750 training images and 25,250 testing images).

And our goal is beating DeepFood, a 2016 paper which used a Convolutional Neural Network trained for 2-3 days
to achieve 77.4% top-1 accuracy.

Alongside attempting to beat the DeepFood paper, we're going to learn about two methods to significantly improve the speed of our model training:

1. Prefetching
2. Mixed precision training

### Project Informatiom:
* Dataset source --> TensorFlow Datasets
* Train data -->	75,750 images
* Test data	--> 25,250 images
* Mixed precision -->	Yes
* Data loading --> Performanant tf.data API
* Target results --> 77.4% top-1 accuracy (beat DeepFood paper)

### GPU Informatiomn:
Before we can move forward if we want to use mixed precision training, we need to make sure the GPU powering our Google Colab instance (if we're using Google Colab) is compataible.

For mixed precision training to work, we need access to a GPU with a compute compability score of 7.0+.

Google Colab offers P100, K80 and T4 GPUs, however, the P100 and K80 aren't compatible with mixed precision training.

Therefore before we proceed we need to make sure we have access to a Tesla T4 GPU in our Google Colab instance.

**Note:** If we run the cell and see a P100 or K80, try going to to Runtime -> Factory Reset Runtime (note: this will remove any saved variables and data from your Colab instance) and then retry to get a T4.

## What we're going to cover
* Using TensorFlow Datasets to download and explore data
* Creating preprocessing function for our data
* Batching & preparing datasets for modelling (making our datasets run fast)
* Creating modelling callbacks
* Setting up mixed precision training
* Building a feature extraction model (see transfer learning part 1: feature extraction)
* Fine-tuning the feature extraction model (see transfer learning part 2: fine-tuning)
* Viewing training results on TensorBoard
