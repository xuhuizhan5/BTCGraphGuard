# BTCGraphGuard

## Classifying Illicit Bitcoin Transactions using Graph Neural Networks

### Overview

BTCGraphGuard is a project focused on detecting illicit activities on the Bitcoin blockchain through advanced graph neural network (GNN) techniques. Using the Elliptic Dataset, we implement and compare various GNN architectures to classify Bitcoin transactions as either "licit" or "illicit" with high accuracy, even when dealing with a large number of unlabeled transactions.

### Features

- Implementation of multiple GNN architectures:
  - Graph Convolutional Networks (GCN)
  - Graph Attention Networks (GAT)
  - Temporal GNNs
- Comprehensive Bitcoin transaction analysis
- Classification of unlabeled transactions
- Graph-level property analysis (degree distributions, clusters, centrality)
- Similarity assessment between subgraphs predicted by different models

### Dataset

The project utilizes the Elliptic Data Set (https://www.kaggle.com/datasets/ellipticco/elliptic-data-set/data), which contains:

- 203,769 nodes and 234,355 edges
- 166 features per node (transactional and aggregated features)
- Labels: Illicit (2%), Licit (21%), Unknown (77%)

### Methodology

Our approach consists of:

1. Data preprocessing and exploration
2. Training GNN models on labeled data
3. Predicting labels for unknown transactions
4. Analyzing graph-level properties
5. Assessing similarities and differences among predicted subgraphs

### Installation

```bash
# Clone the repository
git clone git@github.com:xuhuizhan5/BTCGraphGuard.git
cd BTCGraphGuard

# Create and activate a virtual environment (optional but recommended)
python -m venv env
source env/bin/activate  # On Windows, use: env\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Usage

```bash
# Run data preprocessing
python src/preprocessing.py

# Train the baseline GCN model
python src/train_gcn.py

# Train the GAT model
python src/train_gat.py

# Train the Temporal GNN model
python src/train_temporal_gnn.py

# Evaluate and compare models
python src/evaluate_models.py
```

### Project Structure

```
BTCGraphGuard/
├── data/               # Dataset files
├── notebooks/          # Jupyter notebooks for exploration and analysis
├── src/                # Source code
│   ├── models/         # GNN model implementations
│   ├── preprocessing.py
│   ├── train_gcn.py
│   ├── train_gat.py
│   ├── train_temporal_gnn.py
│   └── evaluate_models.py
├── results/            # Saved model outputs and visualizations
├── requirements.txt    # Project dependencies
└── README.md           # Project documentation
```

### Timeline

| Date                                 | Task                                                      |
| ------------------------------------ | --------------------------------------------------------- |
| **Mar 25 (Proposal)**          | Submit proposal; Data exploration                         |
| **Mar 25 - Apr 1**             | Data preprocessing; implement baseline GCN                |
| **Apr 1 (Project Update)**     | Preliminary results with GCN; basic dataset analysis      |
| **Apr 2 - Apr 8**              | Implement Graph Attention Networks (GAT)                  |
| **Apr 9 - Apr 14**             | Implement Temporal GNN; Initial comparisons               |
| **Apr 15 & 17 (Presentation)** | Present methods and preliminary findings                  |
| **Apr 16 - Apr 22**            | Predict unknown nodes; compare predicted subgraphs        |
| **Apr 23 - Apr 25**            | Analyze graph similarity across methods; finalize results |
| **Apr 25 (Final Submission)**  | Submit code, documentation, and final paper               |

### Contributors

- Xuhui Zhan
- Siyu Yang
- Tianhao Qu

### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Note:** This project aims to enhance understanding of GNN performance in financial anomaly detection and provide insights into structural similarities between predicted illicit transaction networks.
