# Aerial Imagery Classification of Cactus

## Overview
This project aims to identify a specific type of cactus, *Neobuxbaumia tetetzo*, in aerial imagery. Accurate identification of this cactus species is essential for understanding the impact of climate change and human activities on protected natural areas.

## Dataset
The dataset includes labeled training images and unlabeled test images, with 32 x 32 thumbnails of aerial photos. A preliminary analysis revealed a class imbalance: 75% of images depict cacti. Various methods were implemented to address this imbalance and improve model performance.

## Data Preprocessing
To enhance model accuracy, several preprocessing methods were applied:
1. **Oversampling and Undersampling:** Addressed the class imbalance by increasing minority class samples or reducing majority class samples.
2. **Normalization:** Scaled pixel values to a standard range to stabilize model training.
3. **Histogram Equalization:** Improved contrast by redistributing pixel intensity values.

## Model
The **ResNet18** architecture was selected for its efficiency in feature extraction and manageable number of parameters. Initially, a simple model was tested, followed by ResNet18 with varying numbers of fully connected (FC) layers for the classification head. Different configurations were evaluated to identify the best model architecture.

## Results
The combination of **Normalization** and **Histogram Equalization** provided the highest model performance, achieving near-perfect results. Among the tested architectures, **ResNet18 with two FC layers** performed best, with an AUC of 0.9998 on validation data.

## Experiments
To further enhance performance, unlabeled test samples were classified using the custom-trained model. These labels were used to retrain the model, though the additional synthetic data slightly decreased recall while improving precision. This result highlighted the trade-offs between high recall and high precision in classification tasks.

## Conclusion
This project identified the best preprocessing methods and model configurations for the cactus classification task in aerial imagery. Future work could explore advanced unsupervised clustering techniques to improve unlabeled sample classification, enhancing model robustness.
