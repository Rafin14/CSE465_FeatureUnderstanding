# CSE465_FeatureUnderstanding

# CSE465_FeatureUnderstanding

## Project Overview
This project explores feature hierarchies in deep learning models, specifically using ResNet-18 on the CIFAR-10 dataset. It includes visualizations of feature maps, embeddings, and projections using techniques like t-SNE and UMAP.

## Folder Structure
- **Feature_Heirarchy_ResNet_Cifar10.ipynb**: Notebook for analyzing feature hierarchies in ResNet-18.
- **ResNet_Cifar10.ipynb**: Notebook for extracting embeddings and visualizing projections.
- **data/**: Contains CIFAR-10 dataset files.
- **embeddings/**: Precomputed embeddings and labels for CIFAR-10 using ResNet-18.

## Key Features
1. **Feature Map Visualization**:
   - Forward hooks are registered on ResNet-18 layers to extract feature maps.
   - Feature maps are plotted for selected layers.

2. **Embeddings Extraction**:
   - ResNet-18 is used to extract embeddings from CIFAR-10 images.
   - Embeddings are saved in `.npy` format.

3. **Dimensionality Reduction**:
   - t-SNE and UMAP are applied to visualize embeddings in 2D space.
   - Scatter plots are generated to show class separability.

## Dependencies
- Python 3.10
- PyTorch
- Torchvision
- Matplotlib
- NumPy
- Seaborn
- UMAP-learn
- Scikit-learn

## How to Run
1. Download the CIFAR-10 dataset:
   ```bash
   python Feature_Heirarchy_ResNet_Cifar10.ipynb