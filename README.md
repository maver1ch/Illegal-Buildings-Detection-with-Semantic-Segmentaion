# Illegal Building Detection in Satellite Images using Deep Learning Models

This project focuses on the automatic detection and segmentation of illegal buildings from satellite images using deep learning models. The primary goal is to assist local authorities in detecting and managing illegal construction activities more efficiently, particularly in urban areas of **Hanoi, Vietnam**. By utilizing U-Net and LinkNet models, the project demonstrates the potential of deep learning to improve building detection in satellite imagery.

## About The Project

In rapidly urbanizing areas like Hanoi, the detection of illegal buildings is a significant challenge for local authorities. Unauthorized construction not only disrupts urban planning but also has negative environmental and social consequences. Traditional methods, including manual inspection and UAV imagery analysis, are time-consuming and prone to errors.

This project leverages **deep learning models**, specifically **U-Net** and **LinkNet**, to automate the detection and segmentation of buildings from satellite images. The primary dataset used for this project consists of satellite imagery from districts in Hanoi, which has been labeled to distinguish buildings from other land covers.

### Main Steps Involved:
- **Data Collection**: Satellite images of four districts in Hanoi (Ha Dong, Cau Giay, Hoang Mai, Hoan Kiem) were collected using Google Earth Pro. The dataset includes over 200 images, with a total of approximately 2000 smaller image segments after augmentation.
- **Data Preprocessing**: Images were cut into smaller segments, resized, and augmented by 180-degree rotations to increase the size of the training dataset.
- **Modeling**: The project employs U-Net and LinkNet with EfficientNetB7 backbones for building detection and segmentation in satellite images.
- **Evaluation**: The models are evaluated using accuracy and binary cross-entropy loss, with comparisons between U-Net and LinkNet architectures.
- **Challenges and Future Work**: The project faces limitations due to the small and non-diverse dataset and constrained computational resources. Despite these challenges, promising results have been achieved.


## Dataset

The dataset consists of satellite images from four districts of Hanoi: **Ha Dong**, **Cau Giay**, **Hoang Mai**, and **Hoan Kiem**. The dataset was split into 80% for training and 20% for validation.

- **Total Images**: ~2000 (including augmentations)
- **Image Size**: 1096x768 pixels, viewed from a height of 2000 feet.
- **Augmentation**: 180-degree rotation to enhance the training set.


## Deep Learning Models

### 1. **U-Net**
U-Net is a fully convolutional network that excels at image segmentation tasks. It features a symmetric encoder-decoder architecture with skip connections that help capture both low-level and high-level features, making it highly effective for tasks requiring detailed segmentation, such as building detection in satellite images.

### 2. **LinkNet**
LinkNet also employs an encoder-decoder structure but is more lightweight than U-Net, making it suitable for scenarios with limited computational resources. By linking encoder and decoder layers directly, LinkNet retains spatial information with reduced complexity.

## Model Training and Validation

- **Training Environment**: Models were trained on Google Colab using TPU v2 instances with limited runtime and RAM.
- **Evaluation Metrics**:
  - **Accuracy (A)**: Measures the proportion of correctly classified pixels.
  - **Binary Cross-Entropy Loss**: A loss function used for segmentation tasks involving binary classification of pixels.

The results for both models in terms of accuracy are shown below:

| Model    | Accuracy |
|----------|----------|
| U-Net    | 92.25%   |
| LinkNet  | 91.99%   |

## Results and Discussion

Both U-Net and LinkNet demonstrated strong performance in building detection. However, U-Net outperformed LinkNet slightly in terms of accuracy. The models were evaluated based on both quantitative metrics (accuracy and loss) and qualitative results (visual comparison of segmentation masks).

**Challenges** faced during the project included:
- **Dataset Limitations**: The dataset was small and lacked diversity in terms of building types, angles, and lighting conditions.
- **Computational Constraints**: Google Colab's free tier posed runtime limitations that affected training efficiency.

### Potential Applications

The project has numerous applications, including:
- **Urban Planning**: Assisting city planners in managing urban growth and detecting illegal buildings.
- **Municipal Services**: Providing data on building locations for improved public service delivery.
- **Telecommunications**: Informing decisions on the placement of transmission stations and communication infrastructure.
