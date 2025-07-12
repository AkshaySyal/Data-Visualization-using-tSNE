# Data-Visualization-using-tSNE
The project involves applying t-SNE (t-Distributed Stochastic Neighbor Embedding) for non-linear dimensionality reduction to MNIST image data and TF-IDF vectorized 20 Newsgroups text data, generating 2D or 3D representations for visualization with varying perplexity values.

# Problem Statement
<img width="1573" height="429" alt="image" src="https://github.com/user-attachments/assets/36517d90-3e5e-4830-aa5e-3b403d68e2ec" />

# Solution Summary
- Applied **t-Distributed Stochastic Neighbor Embedding (t-SNE)** for:
  - Non-linear dimensionality reduction
  - 2D and 3D data visualization

- **Datasets Used**:
  - **MNIST** (handwritten digits)
  - **20 Newsgroups (20NG)** (text collection)

- **Data Preprocessing**:
  - MNIST:
    - Reshaped images to 2D array.
    - Normalized pixel values (divided by 255.0).
  - 20NG:
    - Cleaned text with regex (removed non-alphanumeric, newlines).
    - Lowercased, tokenized, removed stopwords, filtered valid words (using NLTK’s WordNet).
    - Transformed into **TF-IDF features** → sparse matrix (11314 × 32863, sparsity ~0.9983).

- **t-SNE Execution**:
  - Explored varying `perplexity` values:
    - 5, 20, 100
  - Set `n_components` to 2 or 3 for visualization.
  - Tracked verbose outputs:
    - Number of nearest neighbors (e.g., 16 for perplexity 5, 61 for 20 on MNIST).
    - Mean sigma values (e.g., 1.105785 for perplexity 5, 1.535787 for 20).
    - KL divergence progression during optimization.
  - For high perplexity (100) on MNIST, used **10,000-sample subset** to manage compute load.

- **Visualization**:
  - Plotted reduced data points, colored by true labels.
  - Tools:
    - **Matplotlib** for static 2D scatter plots.
    - **Plotly Express** for interactive 3D scatter plots (especially 20NG).
  - Enabled clear visual assessment of **class separation** in low-dimensional space.

- **Conclusion**:
  - Demonstrated t-SNE’s power to uncover hidden structure and visualize complex datasets.
  - Highlighted the effect of perplexity on embeddings and the trade-off between computation and interpretability.
