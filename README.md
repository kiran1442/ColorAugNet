# ColorAugNet : Improving Grayscale Image Colorization via Data Augmentation

## Project Overview

**ColorAugNet** is a deep learning project aimed at enhancing the colorization of grayscale images by leveraging dataset augmentation techniques. This project compares model performance with and without data augmentation to demonstrate its impact on colorization quality.

The CIFAR-10 dataset is used as a base, and the model converts grayscale images to RGB by learning from the original color data. Augmentation techniques like rotation, flipping, and shifting are used to synthetically increase dataset diversity.

---

## Objective

- **Train a convolutional neural network** to colorize grayscale images.
- **Improve colorization quality** by applying data augmentation to the training set.
- **Compare results** with and without augmentation using visual examples and SSIM scores.

---

## Dataset

- CIFAR-10 dataset
- **Image Dimensions**: 32x32 RGB
- The dataset is preprocessed by:
  - Normalizing pixel values.
  - Converting RGB to grayscale for input.
  - Augmenting RGB images and converting them to grayscale for the augmented set.

---

## Model Architecture

A custom convolutional neural network (CNN) was built for image-to-image translation. It includes:
- 3 convolutional layers with increasing filters.
- Batch normalization for improved convergence.
- A final `Conv2D` layer with sigmoid activation to output RGB images.

Loss Function:
- **SSIM (Structural Similarity Index)** loss is used to prioritize perceptual image quality.

---

## Augmentation Techniques

Implemented using `ImageDataGenerator`:
- Rotation (up to 20°)
- Width & height shifting (10%)
- Horizontal flipping

---


### Training Performance

- Model trained for 5 epochs with augmented data and without augmented data.
- Visual improvement in color saturation and sharpness.
- SSIM metric used for quantitative evaluation.

```bash
Average SSIM Score: 0.9032 (with augmentation)
