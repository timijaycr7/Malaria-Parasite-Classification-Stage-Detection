# Malaria Parasite Classification & Stage Detection
<img width="624" height="226" alt="image" src="https://github.com/user-attachments/assets/c86b5232-c277-4c7d-81d3-4050b05407a5" />

# Overview

This repository presents a hierarchical machine learning framework for automated malaria diagnosis from stained microscopic blood smear images. The system is designed to replicate the diagnostic workflow used by malaria experts by first identifying parasite species and subsequently detecting infection stages and parasite localization within red blood cells.

The framework integrates deep learning and traditional machine learning models to provide a modular, scalable, and accurate end-to-end diagnostic pipeline suitable for clinical and research applications.

# 🎯 Objectives

Automate malaria parasite species classification

Detect parasite infection stages within blood cells

Localize parasites spatially in microscopic images

Compare deep learning and traditional ML approaches

Improve robustness under limited annotated data

# 🧠 System Architecture

The framework follows a two-level hierarchical pipeline:

# Level 1:  Parasite Species Classification

Each microscopic image is first classified into:

Plasmodium falciparum

Plasmodium ovale

Plasmodium malariae

Plasmodium vivax

Uninfected cells

Two approaches are implemented:

# ✅ Deep Learning Approach (ResNet Backbone)

Convolutional neural network with residual connections

Learns morphological patterns such as:

parasite texture

chromatin distribution

staining variation

cell shape features

Acts as a decision gate routing samples to stage detection models

# ✅ Traditional Machine Learning Approach

Random Forest and XGBoost classifiers

Operate on handcrafted HOG feature representations

Provide fast, low-resource inference

# Level 2:  Infection Stage Detection & Localization

After species identification, images are routed to species-specific detection models that:

Identify parasite life-cycle stages:

Ring

Trophozoite

Schizont

Gametocyte

Localize parasites within the blood cell

Detection architectures include:

Faster R-CNN

RT-DETR

YOLO-based detectors

This specialization minimizes inter-species confusion and improves detection precision.

# 🔧 Data Preprocessing & Augmentation

To overcome limited annotated medical imaging data, extensive enhancement strategies were applied:

Preprocessing

Image resizing

Pixel normalization

Stain enhancement

Noise reduction

Grayscale conversion (for traditional models)

Augmentation

Random rotations

Horizontal & vertical flips

Scaling and cropping

Brightness & contrast adjustment

Stain intensity variation

These techniques improve generalization and reduce overfitting.

# 📊 Key Insights
Deep Learning Models

✔ Strong spatial feature learning
✔ Robust against staining variation
✔ Better morphology representation

# Traditional Models

✔ Fast and lightweight
✔ CPU-friendly
❗ Limited spatial understanding
❗ Sensitive to illumination and noise
