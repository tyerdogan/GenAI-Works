# Diffusion, PixelCNN, and Transformers

This notebook implements three different generative models for image and text generation.

## Table of Contents
1. [Diffusion Model (CelebA)](#diffusion-model)
2. [PixelCNN (CelebA)](#pixelcnn)
3. [Transformer Language Model (Shakespeare)](#transformer-lm)

---

## 1. Diffusion Model (CelebA)
**Objective:** Generate realistic human faces using a Denoising Diffusion Probabilistic Model (DDPM).

- **Architecture:** U-Net with time-step embeddings and residual connections.
- **Method:** Trains to reverse a linear noise schedule (Gaussian noise).
- **Key Results:**
  - Visualizes forward diffusion (adding noise).
  - Generates novel faces starting from pure noise.
  - Comparisons with nearest training neighbors to verify novelty.

## 2. PixelCNN (CelebA)
**Objective:** Autoregressive image generation by modeling the conditional distribution of pixels.

- **Architecture:** Convolutional network with Masked Convolutions (Type A & B) to preserve autoregressive ordering.
- **Method:** Predicts pixel values pixel-by-pixel (raster scan order).
- **Key Results:**
  - trained on quantized CelebA images (8 levels).
  - Generates samples with variable temperatures.
  - Analyzes likelihood (Bits-per-dimension) across different attributes (e.g., Male vs Female).

## 3. Transformer Language Model (Shakespeare)
**Objective:** Character-level text generation using a Decoder-only Transformer.

- **Architecture:** Multi-head Causal Self-Attention mechanism with Pre-LayerNorm.
- **Method:** Next-token prediction on the Tiny Shakespeare dataset.
- **Key Results:**
  - Text generation using Temperature, Top-K, and Nucleus (Top-P) sampling.
  - Perplexity evaluation on validation data.
  - Analysis of context length impact on generation coherence.
