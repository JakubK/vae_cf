# Fork of "Variational autoencoders for collaborative filtering"

This repository is a fork of the code originally accompanying the paper 
"[Variational autoencoders for collaborative filtering](https://arxiv.org/abs/1802.05814)" by Dawen Liang, Rahul G. Krishnan, Matthew D. Hoffman, and Tony Jebara, in The Web Conference (aka WWW) 2018."

See last section for the original README contents

## Introduction

This fork of the repository aims to update the original code, which was designed for older versions of Python and TensorFlow, making it compatible with the latest Python and TensorFlow versions, particularly for use in platforms like Google Colab.

## Changes Made

- Refactored Pandas data preparation code cells to be executable
- Preinstall `bottleneck` package used in this notebook
- Add cell for fetching and unzipping the dataset
- Fix hyperparameter setup
- Fix MultiDAE and MultiVAE regularization step
- Add `tqdm` for more readable training tracking
- Add 1e-6 to divisors when calculating NDCG and Recall to fix NaN values issue
- Attached `requirements.txt`

## Evaluation

The notebook should be ready to go as is in Google Colab (T4 GPU instance recommended, available in free version of Google Colab).
Executing all code in notebook takes about 4 hours in T4 instance.

The results of validation NDCG per epoch, test NDCG and test Recall are not exactly the same like those displayed in the original notebook, but are very close.

## Main package versions (from requirements.txt)

- Pandas - 1.5.3
- Tensorflow - 2.14.1

# Original README
# Variational autoencoders for collaborative filtering

This notebook accompanies the paper "[Variational autoencoders for collaborative filtering](https://arxiv.org/abs/1802.05814)" by Dawen Liang, Rahul G. Krishnan, Matthew D. Hoffman, and Tony Jebara, in The Web Conference (aka WWW) 2018.

In this notebook, we show a complete self-contained example of training a variational autoencoder (as well as a denoising autoencoder) with multinomial likelihood (described in the paper) on the public Movielens-20M dataset, including both data preprocessing and model training.
