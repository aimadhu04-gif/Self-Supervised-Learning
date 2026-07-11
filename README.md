# 🃏 Self-Supervised Learning on Card Images

![Python](https://img.shields.io/badge/Python-3.10-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-DeepLearning-red)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A **Self-Supervised Learning (SSL)** project that trains a model to understand playing card images **without using any labels**, using the **SimCLR** contrastive learning approach — then evaluates the learned features through linear classification.

---

## 📌 Overview

Traditional supervised learning needs labeled data. This project shows how a model can learn meaningful visual features **purely from the images themselves**, by comparing augmented versions of the same image against others.

| Phase | Description |
|-------|-------------|
| **Phase 1 — Self-Supervised Pretraining** | ResNet18 encoder trained from scratch using SimCLR (contrastive learning + NT-Xent loss) on unlabeled card images |
| **Phase 2 — Linear Evaluation** | Encoder frozen, a linear classifier trained on top to measure how good the learned features are |

---

## 🗂️ Dataset

- 🎴 **53-class** playing card dataset (Ace, King, Queen, Jack, Joker, etc.)
- 📊 **7,624** train images | **265** test images | **265** validation images
- 🖼️ Image size: `200 x 200 x 3`

---

## 📈 Results

### Self-Supervised Pretraining (SimCLR)
| Epochs | Initial Loss | Final Loss |
|--------|-------------|------------|
| 20 | 4.33 | 3.73 |

### Linear Evaluation (Frozen Encoder + Classifier)
| Metric | Score |
|--------|-------|
| Train Accuracy | **41.53%** |
| Test Accuracy | **34.72%** |

> 🎯 With 53 classes, random guessing gives ~1.9% accuracy — this model performs **~18x better**, showing the SSL encoder learned meaningful card features without any labels.

---

## 🛠️ Tech Stack

- **Python**, **PyTorch**, **Torchvision**
- **ResNet18** — custom-trained encoder (no pretrained weights)
- **SimCLR** — Contrastive Self-Supervised Learning
- **NT-Xent Loss** — contrastive loss function

---

## 🚀 Pipeline
