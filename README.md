This project involves the analysis of single-cell RNA sequencing data from three different samples: Lactone, Control, and Saline. The analysis is conducted using the Seurat package in R, which is a popular toolkit for single-cell genomics. The objective is to integrate and compare the data across these samples to identify differentially expressed genes and cluster cells based on their gene expression profiles.
Feel free to browse the script (Project_25_03_23.Rmd).
To request the data files and other questions contact me.

## Data Preprocessing

1. **Reading Data**: The data is read from the specified directories using the `Read10X` function, which reads the 10X Genomics output.

2. **Creating Seurat Objects**: Seurat objects are created for each sample with a minimum threshold for cells and features to filter out low-quality data.

3. **Merging Data**: The individual Seurat objects are merged into a single object to facilitate integrated analysis.

## Normalization and Integration

1. **Splitting and Normalization**: The combined dataset is split into individual objects based on sample types, and each object is normalized using the SCTransform method, which helps to correct for technical noise and variability.

2. **Feature Selection and Integration Preparation**: The top 3000 variable features are selected, and the datasets are prepared for integration.

3. **Finding Integration Anchors and Data Integration**: Integration anchors are identified, and the datasets are integrated to create a unified dataset, allowing for comparisons across conditions.

## Dimensionality Reduction and Clustering

1. **PCA and UMAP**: Principal Component Analysis (PCA) is performed for dimensionality reduction, and Uniform Manifold Approximation and Projection (UMAP) is used for visualization.

2. **Finding Neighbors and Clustering**: Nearest neighbors are found based on the PCA results, and clustering is performed to group similar cells together.

## Differential Gene Expression Analysis

1. **Identifying Markers**: Differentially expressed genes are identified for each cluster. These markers are further annotated using an external dataset to add biological context.

2. **Cluster Identification**: Clusters are renamed based on known cell types, and key marker genes for each cell type are visualized using feature plots.

## Statistical Analysis and Visualization

1. **Differential Expression Between Conditions**: Differential expression analysis is conducted to compare gene expression between conditions (e.g., Lactone vs. Control).

2. **Visualization**: Various plots are generated, including UMAP plots, volcano plots, and violin plots, to visualize the gene expression patterns and differences across conditions and clusters.

## Conclusion

This analysis pipeline provides a comprehensive approach to single-cell RNA sequencing data analysis, from data preprocessing and integration to clustering and differential expression analysis. The methods implemented allow for the identification of key biological differences between samples, providing insights into cellular responses and gene expression dynamics.
