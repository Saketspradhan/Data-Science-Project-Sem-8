# Data Science Project: Medical Image Segmentation with Vision Transformers

This repo reproduces the results of  [TransUNet: Transformers Make Strong Encoders for Medical Image Segmentation](https://arxiv.org/pdf/2102.04306.pdf) as a final project for the course Deep Learning in Data Science DD2424 @ KTH (Royal Institute of Technology)

## Environment

The project is implemented with Tensorflow 2. med-py library is used for medical image segmentation evaluation (Hausdorf Distance and Dice Score).
Prepare an virtual environment with python>=3.8, and then use the following command line for the dependencies.

## Data 

The  experiments were conducted on Synapse multi-organ segmentation dataset.

* Access to the synapse multi-organ dataset:

  * Sign up in the [official Synapse website](https://www.synapse.org/#!Synapse:syn3193805/wiki/) and download the dataset. Convert them to numpy format, clip the images within [-125, 275], normalize each 3D image to [0, 1], and extract 2D slices from 3D volume for training cases while keeping the 3D volume in h5 format for testing cases.
  * Set up a Google Cloud Project to store your data in a bucket.
  * Convert the data from numpy to TfRecords (Tensorflow’s binarystorage format) to speed up training and enable parallel data reading from disk. A data parasing pipeline is provided to write and read TfRecords as a TFDataset in the module data_processing module.
