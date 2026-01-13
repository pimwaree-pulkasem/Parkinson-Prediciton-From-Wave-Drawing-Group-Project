# Parkinson Prediction from Wave Drawing

## Project Overview
This project focuses on predicting Parkinson’s disease using wave drawing images. The main idea is that people with Parkinson’s disease tend to draw unsteady or irregular wave patterns compared to healthy individuals. By applying image preprocessing, data augmentation, and deep learning models, the system aims to classify wave drawings into two categories: **Healthy** and **Parkinson**.

The project was developed as a group assignment under the team name **WE WORK HARD BUT PUNCH’S LAPTOP WORKS HARDER**.

## Objective
- Analyze wave drawing patterns
- Train deep learning models to classify drawings as Healthy or Parkinson
- Compare multiple CNN-based architectures and select suitable models

## Dataset
The dataset consists of wave drawing images collected from public Kaggle sources:
- Parkinson’s Drawings Dataset
- Additional related drawing datasets from Kaggle

### Dataset Characteristics
- Image type: Wave drawings
- Original image size: 512 pixels (unsteady drawings)
- Classes:
  - Healthy
  - Parkinson
- Initial dataset size:
  - Wave images: 102 images
- Class distribution is balanced for both training and test sets

### Data Augmentation
Because the original dataset was very small, augmentation was applied **only to the training set**.

After augmentation:
- Total images: 1,542
- Training set: 1,210 images
- Validation set: 302 images
- Test set: 30 images

## Preprocessing Steps
The following preprocessing techniques were applied:
- Image inversion
- Dilation
- Normalization
- Conversion to RGB format (required for pretrained models)

## Models Used
Several deep learning models were implemented and compared:

### 1. CNN (Custom Model)
- Initial problem: Overfitting
- Solutions applied:
  - Added Dropout
  - Added Batch Normalization
  - Reduced learning rate
- Result: More stable training and reduced overfitting

### 2. MobileNetV2 (Pretrained)
- Lightweight and efficient
- Validation accuracy up to approximately 95%
- Test accuracy around 90%
- Some overfitting observed when training accuracy exceeded 99%

### 3. ResNet50 (Pretrained)
- Strong performance with deeper architecture
- After tuning, overfitting was minimized
- Achieved high validation accuracy and stable loss

## Model Performance Summary
| Model        | Epochs | Pretrained | Test Accuracy | Train Accuracy | Validation Accuracy |
|-------------|--------|------------|---------------|----------------|---------------------|
| ResNet50    | 50     | Yes        | 0.9333        | 0.98           | 0.96                |
| CNN         | 32     | No         | 0.76          | 0.9673         | 0.9503              |
| MobileNetV2 | 20     | Yes        | 0.9125        | 0.97           | 0.94                |

## Selected Models
Based on overall performance and stability, the selected models are:
- ResNet50
- MobileNetV2

## Limitations
- Original dataset size was very small
- Test set size is limited, which may affect generalization
- Model performance may vary with real-world data
## Presentation 
- Google Drive: https://drive.google.com/file/d/1nxnddFqV4rAfXOuRf62AKU-wL4S19yYn/view?usp=drive_link

## Team Members
- Pimwaree – CNN Model
- Variyaporn – ResNet50 Model
- Patcharee – MobileNetV2 Model

## Conclusion
This project demonstrates that wave drawing images can be effectively used with deep learning techniques to assist in Parkinson’s disease prediction. With sufficient data and further validation, such approaches 

could support early screening and research applications.

