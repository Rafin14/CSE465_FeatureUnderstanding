# Visual Embeddings in CNNs: Similarity and Feature Understanding

## Project Overview
This project focuses on extracting and analyzing the final-layer embeddings of various Convolutional Neural Network (CNN) architectures to understand image similarity and feature representation. By utilizing **Transfer Learning**, the study evaluates how different models perceive visual data and whether their internal feature understanding is consistent across diverse datasets.

## Key Objectives
*   **Feature Extraction:** Analyze final-layer visual embeddings for image similarity.
*   **Transfer Learning Evaluation:** Compare the performance of pre-trained models on **Caltech-101** and **CIFAR-10** datasets.
*   **Dimensionality Reduction & Visualization:** Use **UMAP** and **t-SNE** to visualize class clustering and feature separation across different architectures.
*   **Semantic Similarity:** Compare nearest neighbor retrieval results across models to see if they align with human-perceived semantic similarity.

## Models & Architectures
The project evaluates three prominent CNN architectures:
1.  **ResNet-101**
2.  **GoogLeNet (Inception)**
3.  **ZFNet**

## Datasets
*   **Caltech-101:** Approximately 9,145 images across 102 classes. Images were resized to 224×224×3 for model compatibility.
*   **CIFAR-10:** 60,000 images across 10 classes. Tiny 32x32 images were upsampled to 224×224×3 for the pre-trained models.

## Methodology
### Regularization & Optimization
*   **Regularization:** Techniques included freezing the convolutional backbones for all models, implementing dropout, L2 weight decay (for ZFNet), and batch normalization (for ResNet-101).
*   **Optimization:** The training utilized the **Adam** optimizer, **CrossEntropyLoss**, and **StepLR** learning rate scheduling.

## Performance Analysis
### Transfer Learning Results
ResNet-101 demonstrated the strongest performance across both datasets.

| Dataset | Model | Test Accuracy | Weighted F1-Score | Mean ROC AUC |
| :--- | :--- | :--- | :--- | :--- |
| **Caltech-101** | GoogLeNet | 98.36% | 0.9835 | 0.9999 |
| **Caltech-101** | ResNet-101 | **99.51%** | **0.9951** | 0.9986 |
| **Caltech-101** | ZFNet | 87.30% | 0.8735 | 0.9905 |
| **CIFAR-10** | GoogLeNet | 80.80% | 0.8072 | 0.9817 |
| **CIFAR-10** | ResNet-101 | 85.42% | 0.8537 | 0.9882 |
| **CIFAR-10** | ZFNet | 87.30% | 0.8735 | 0.9905 |

*Note: While ZFNet shows a high accuracy on CIFAR-10, visualizations indicate its features are more scattered compared to ResNet-101.*

### Key Observations
*   **Clustering Trends:** ResNet-101 consistently produced better feature separation in UMAP and t-SNE visualizations. CIFAR-10 showed more compact clusters than Caltech-101 due to having fewer classes.
*   **Semantic Retrieval:** Nearest neighbor comparisons showed that GoogLeNet and ResNet-101 effectively retrieved semantically similar images (e.g., wild cats), while ZFNet results were more varied and less relevant.
*   **Architecture Impact:** Model architecture significantly impacts clustering; ResNet-101 was found to be the most cohesive, whereas GoogLeNet and ZFNet often produced more scattered embeddings.

## Conclusion
The study concludes that **ResNet-101** outperforms GoogLeNet and ZFNet in both raw classification accuracy and the quality of feature embeddings. Clearer feature clustering in latent space directly correlates with improved nearest neighbor retrieval and overall model robustness.

## Future Work
*   Explore more recent architectures such as **EfficientNet** and **Vision Transformers (ViT)** for enhanced embeddings.
*   Experiment with advanced fine-tuning, such as unfreezing specific layers or using domain-specific loss functions.
*   Apply embedding-based analysis to real-world applications like zero-shot learning and anomaly detection.
