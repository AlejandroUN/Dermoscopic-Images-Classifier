# Dermoscopic Images Challenge

This project aims to classify images of skin lesions into 8 categories using a variety of machine learning models, including convolutional neural networks (CNNs) and traditional methods like Support Vector Machines (SVM). The dataset consists of dermoscopic images and metadata (age, sex, lesion location) that are used to train and evaluate the models.

If you want to know more about this project you could take a look at the final report here: [**Final Report**](https://github.com/AlejandroUN/Dermoscopic-Images-Classifier/blob/main/Projet_IMA205_CHAVEZ_Cristian%20(1).pdf)


<p align="center">
  <img src="https://raw.githubusercontent.com/AlejandroUN/Dermoscopic-Images-Classifier/refs/heads/main/example.png" alt="image"/>
</p>


## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Models Implemented](#models-implemented)
  - [Preprocessing](#preprocessing)
  - [Classification Methods](#classification-methods)
- [Results](#results)
- [How to Run](#how-to-run)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)

## Overview
This project involves using machine learning to classify skin lesions into 8 different categories, including melanoma, basal cell carcinoma, and others. Several models are implemented, including CNNs such as ResNet, DenseNet, and ResNeXt, as well as SVMs. The best-performing model was ResNeXt, achieving the highest accuracy on both the public and private leaderboards.

## Dataset
The dataset contains dermoscopic images classified into 8 different categories:
1. Melanoma
2. Melanocytic nevus
3. Basal cell carcinoma
4. Actinic keratosis
5. Benign keratosis
6. Dermatofibroma
7. Vascular lesion
8. Squamous cell carcinoma

Each class has a different number of samples, and class imbalance is addressed in the model training process by assigning class weights. The dataset also includes metadata such as the age, sex, and anatomical position of the lesions.

## Models Implemented
### Preprocessing
- **Segmentation**: Otsu thresholding and UNet-based segmentation were implemented. UNet performed better and was used in subsequent stages.
- **Feature Extraction**: ABCD features (Asymmetry, Border irregularity, Color, and Dimension) were extracted from the images.

### Classification Methods
1. **Support Vector Machines (SVM)**:
   - Linear and non-linear kernels were used, with grid search to find optimal hyperparameters.
   
2. **Random Forest**:
   - Implemented but performed poorly due to the complexity of the images.
   
3. **Convolutional Neural Networks (CNNs)**:
   - **DenseNet**
   - **ResNet**
   - **ResNeXt** (Best performing model with a private leaderboard score of 73.1%).

## Results
| Model        | Public Score (%) | Private Score (%) |
|--------------|------------------|-------------------|
| SVM          | 23.1             | 22.4              |
| Random Forest| 20.9             | 20.6              |
| DenseNet     | 61.7             | 58.4              |
| ResNet       | 59.9             | 65.1              |
| ResNeXt      | 73.1             | 73.1              |

ResNeXt, due to its aggregated transformations (cardinality), provided the best results, handling the complex nature of the images better than traditional methods or simpler CNNs.

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/username/repo-name.git
   cd repo-name

