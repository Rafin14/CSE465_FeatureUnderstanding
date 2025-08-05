# CSE465_FeatureUnderstanding

## Project Overview
This project explores feature hierarchies in deep learning models, using ResNet-18, ZFNET & GoogleNet on the CIFAR-10 and Caltech-101 dataset. It includes visualizations of feature maps, embeddings, and projections using techniques like t-SNE and UMAP, along with feature heirarchy visualizations and comparisons.

## Folder Structure
- **Feature_Heirarchy_ResNet_Cifar10.ipynb**: Notebook for analyzing feature hierarchies in multiple models.
- **ResNet_Cifar10.ipynb**: Notebook for extracting embeddings and visualizing projections.
- **data/**: Contains dataset files.
- **embeddings/**: Precomputed embeddings and labels.

## Key Features
1. **Feature Map Visualization**:
   - Forward hooks are registered on model layers to extract feature maps.
   - Feature maps are plotted for selected layers.

2. **Embeddings Extraction**:
   - Pretrained models are used to extract embeddings from dataset images.
   - Embeddings are saved in `.npy` format.

3. **Dimensionality Reduction**:
   - t-SNE and UMAP are applied to visualize embeddings in 2D space.
   - Scatter plots are generated to show class separability.