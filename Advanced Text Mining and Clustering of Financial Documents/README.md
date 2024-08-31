## Overview

This project involves preprocessing, analyzing, and clustering financial documents using text mining techniques. The main goals are to identify important terms within documents, reduce dimensionality, cluster the documents, and perform topic modeling to extract meaningful insights.

## Language Detection

The language of each document is detected using the `langdetect` library. Only documents identified as being in English are retained for further processing. A fixed seed value ensures reproducibility of results across different runs.

## Text Preprocessing

Text preprocessing involves several key steps:

1. **Tokenization:** Breaking down text into smaller units (tokens) such as words or phrases.
2. **Lemmatization:** Reducing words to their base or root forms to ensure consistency.
3. **Stopwords Removal:** Eliminating common words that do not contribute significant meaning to the text.
4. **Punctuation Removal:** Removing punctuation marks that are not necessary for text analysis.

## Tools and Libraries

- **SpaCy:** Used for lemmatization and tokenization. A large English model is employed to enhance accuracy.
- **NLTK:** Provides stopwords and tokenization functionalities.
- **Langdetect:** Detects the language of the text.

## TF-IDF Matrix

**Term Frequency-Inverse Document Frequency (TF-IDF)** is a statistical measure used to evaluate the importance of words in a document relative to a collection of documents. It is composed of two main components:

1. **Term Frequency (TF):** Measures how often a word appears in a document. It can be either raw frequency or normalized to account for document length.
2. **Inverse Document Frequency (IDF):** Measures the importance of a word by considering how common or rare it is across all documents. The formula is IDF = log(N / DF), where N is the total number of documents and DF is the number of documents containing the word.

The TF-IDF matrix is a two-dimensional matrix where rows represent documents and columns represent terms. Each cell indicates the importance of a term in a document.

## PCA (Principal Component Analysis)

PCA is used to reduce the dimensionality of the TF-IDF matrix while preserving 95% of the variance. This process simplifies the data while retaining its essential characteristics. The result is a transformed dataset where the number of dimensions is significantly reduced, making further analysis more manageable.

## Clustering

Different clustering methods are applied to group the documents into clusters:

1. **K-Means Clustering:**
   - **Elbow Method:** Determines the optimal number of clusters by plotting the distortion (inertia) against the number of clusters.
   - **K-Means Implementation:** Assigns documents to clusters based on the specified number of clusters.

2. **DBSCAN (Density-Based Spatial Clustering of Applications with Noise):** 
   - Identifies clusters based on the density of data points, useful for handling noise and varying cluster shapes.

3. **Hierarchical Clustering:**
   - Groups documents into a hierarchy of clusters, which can be visualized as a dendrogram.

## Cluster Evaluation

Clustering results are evaluated using several metrics:

- **Silhouette Score:** Measures how similar a document is to its own cluster compared to other clusters.
- **Calinski-Harabasz Score:** Evaluates the density and separation of clusters.
- **Davies-Bouldin Score:** Measures the average similarity between clusters, with a lower score indicating better clustering.

## t-SNE (t-Distributed Stochastic Neighbor Embedding)

t-SNE is a dimensionality reduction technique used to visualize clusters in two dimensions. It converts the high-dimensional TF-IDF data into a 2D representation, making it easier to interpret cluster separations and relationships visually.

## Topic Modeling

Topic modeling is performed on each cluster to identify and interpret the topics within the documents:

1. **Latent Dirichlet Allocation (LDA):** 
   - A generative probabilistic model that discovers topics based on the distribution of words in documents.

2. **Latent Semantic Analysis (LSA):** 
   - Uses singular value decomposition to identify topics by analyzing the term-document matrix.

3. **Non-Negative Matrix Factorization (NMF):** 
   - Decomposes the matrix into two non-negative matrices, identifying topics based on the decomposition.

## Results

The analysis provides insights into the structure and content of financial documents. By clustering and topic modeling, we can uncover hidden patterns and themes within the data, aiding in better understanding and utilization of financial texts.

