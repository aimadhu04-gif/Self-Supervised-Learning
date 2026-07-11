# Self-Supervised Learning on Card Images

This project demonstrates Self-Supervised Learning (SimCLR-based contrastive learning) 
applied to a 53-class playing card image dataset. The model learns visual representations 
without labels, then is evaluated using linear classification.

## Project Overview

- **Phase 1 - Self-Supervised Pretraining**: A ResNet18 encoder is trained from scratch 
  using SimCLR (contrastive learning with NT-Xent loss) on unlabeled card images.
- **Phase 2 - Linear Evaluation**: The pretrained encoder is frozen, and a linear 
  classifier is trained on top to evaluate the quality of learned features.

## Dataset

- 53-class playing card dataset (Ace, King, Queen, Jack, Joker, etc.)
- 7624 train images, 265 test images, 265 validation images
- Image size: 200 x 200 x 3

## Results

- **Self-Supervised Pretraining (SimCLR)**: 20 epochs, Loss: 4.33 -> 3.73
- **Linear Evaluation (Classifier on frozen encoder)**:
  - Train Accuracy: 41.53%
  - Test Accuracy: 34.72%
- **Backbone**: ResNet18 (trained from scratch, no pretrained weights)

## Tech Stack

- PyTorch, Torchvision
- ResNet18 (custom-trained encoder)
- SimCLR (Contrastive Self-Supervised Learning)
