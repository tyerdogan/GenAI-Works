# Deep Generative Models on CelebA

This project implements, trains, and compares three major classes of deep generative models using the **CelebA** dataset. The goal is to explore different approaches to image generation, density estimation, and representation learning.

## Overview

The notebook covers the implementation of the following models from scratch:

1.  **Variational Autoencoders (VAE)**: A probabilistic framework combining variational inference with deep learning to learn a continuous latent space.
2.  **Generative Adversarial Networks (DCGAN)**: A game-theoretic approach where a Generator and Discriminator compete to produce sharp, realistic images.
3.  **Normalizing Flows (RealNVP)**: A flow-based model using invertible transformations to perform exact likelihood estimation and lossless reconstruction.

## Dataset

*   **Dataset**: CelebA (Large-scale CelebFaces Attributes Dataset)
*   **Preprocessing**: Images are cropped and resized to 32x32 resolution.

## Project Structure

### 1. Variational Autoencoder (VAE)
*   **Architecture**: Convolutional Encoder and Decoder.
*   **Objective**: Maximizing the Evidence Lower Bound (ELBO) consisting of Reconstruction Loss (BCE) and KL Divergence.
*   **Key Results**: Smooth latent space interpolation, stable training, but slightly blurry outputs.

### 2. Generative Adversarial Network (DCGAN)
*   **Architecture**: Deep Convolutional GAN.
*   **Objective**: Minimax game between Generator and Discriminator.
*   **Key Results**: Sharp and high-contrast image generation, though training can be unstable.

### 3. Normalizing Flows (RealNVP)
*   **Architecture**: Multi-scale architecture with Affine Coupling Layers, ActNorm, and Invertible 1x1 Convolutions.
*   **Objective**: Minimizing Negative Log-Likelihood (NLL) via exact inference.
*   **Key Results**: Perfect reconstruction and exact density estimation, susceptible to local artifacts if not trained sufficiently.

## Experiments & Analysis

The project includes comprehensive comparisons across the models:

*   **Sampling**: Generating new, synthetic faces from random noise.
*   **Interpolation**: Morphing between two real faces by traversing the latent space.
*   **Reconstruction**: visualizing how well each model can rebuild an input image.
*   **Likelihood Estimation**: evaluating the models on in-distribution (CelebA) vs. out-of-distribution (FashionMNIST) data.

## Notes

This work is produced for academic purposes as part of coursework.  
Experiments are designed for educational exploration rather than production use.
