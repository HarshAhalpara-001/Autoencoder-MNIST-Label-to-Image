
# MNIST-Autoencoder-LabelGen

A PyTorch project to reconstruct MNIST digits with an autoencoder and generate new digits from labels.

## Overview

This code trains an autoencoder on MNIST images and a `LabelToVector` model to create digits (0–9) from labels using the latent space.

## Requirements

- Python 3.8+
- PyTorch 2.0+ (with CUDA for GPU)
- Torchvision
- Matplotlib

## Installation

1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/MNIST-Autoencoder-LabelGen.git
   cd MNIST-Autoencoder-LabelGen
   ```

2. Install dependencies:
   ```bash
   pip install torch torchvision matplotlib
   ```

## Usage

Run the script to train and generate digits:

```bash
python main.py
```

This will:
1. Train an autoencoder on MNIST digits.
2. Train a `LabelToVector` model to create digits from labels.
3. Show generated images for digits 0–9 and a sample "4".

## How It Works

- **Autoencoder**: Compresses 28x28 MNIST images into a 64-dimensional code and rebuilds them.
- **LabelToVector**: Takes a label (e.g., 4), turns it into a 64-dimensional code, and uses the autoencoder’s decoder to make an image.
- **Training**: The autoencoder learns from images, then `LabelToVector` learns from labels and codes, using a mix of MSE and cosine loss.
