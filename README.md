# BTCGraphGuard

## Classifying Illicit Bitcoin Transactions using Graph Neural Networks

### Overview

BTCGraphGuard is a project focused on detecting illicit activities on the Bitcoin blockchain through advanced graph neural network (GNN) techniques. Using the Elliptic Dataset, we implement and compare various GNN architectures to classify Bitcoin transactions as either "licit" or "illicit" with high accuracy, even when dealing with a large number of unlabeled transactions.

### Features

* Implementation of multiple GNN architectures:
* Graph Convolutional Networks (GCN)
* Graph Attention Networks (GAT)
* GraphSAGE
* Comprehensive Bitcoin transaction analysis
* Classification of unlabeled transactions
* Graph-level property analysis (degree distributions, clusters, centrality)
* Similarity assessment between subgraphs predicted by different models

### Dataset

The project utilizes the Elliptic Data Set (https://www.kaggle.com/datasets/ellipticco/elliptic-data-set/data), which contains:

* 203,769 nodes and 234,355 edges
* 166 features per node (transactional and aggregated features)
* Labels: Illicit (2%), Licit (21%), Unknown (77%)

### Methodology

Our approach consists of:

* Data preprocessing and exploration
* Training GNN models on labeled data
* Predicting labels for unknown transactions
* Analyzing graph-level properties
* Assessing similarities and differences among predicted subgraphs

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

Our entire analysis pipeline is contained within a single Jupyter notebook:

# Launch Jupyter Notebook

jupyter notebook

# Open the main notebook

final_graph.ipynb

### Project Structure

```
BTCGraphGuard/
├── data/                  # Dataset files
│   └── elliptic_bitcoin_dataset/  # Original Elliptic dataset
├── notebooks/             # Additional exploratory notebooks
│   ├── experiment.ipynb
│   └── experiment_with_eda.ipynb
├── final_graph.ipynb      # Main analysis notebook
├── output/                # Saved model outputs and visualizations
├── requirements.txt       # Project dependencies
└── README.md              # Project documentation
```

### Timeline

| Date                                 | Task                                                      |
| ------------------------------------ | --------------------------------------------------------- |
| **Mar 25 (Proposal)**          | Submit proposal; Data exploration                         |
| **Mar 25 - Apr 1**             | Data preprocessing; implement baseline GCN                |
| **Apr 1 (Project Update)**     | Preliminary results with GCN; basic dataset analysis      |
| **Apr 2 - Apr 8**              | Implement Graph Attention Networks (GAT)                  |
| **Apr 9 - Apr 14**             | Implement GraphSAGE; Initial comparisons                  |
| **Apr 15 & 17 (Presentation)** | Present methods and preliminary findings                  |
| **Apr 16 - Apr 22**            | Predict unknown nodes; compare predicted subgraphs        |
| **Apr 23 - Apr 25**            | Analyze graph similarity across methods; finalize results |
| **Apr 25 (Final Submission)**  | Submit code, documentation, and final paper               |

### Contributors

- Xuhui Zhan
- Siyu Yang
- Tianhao Qu

### Acknowledgements

We would like to thank Clem W for sharing their Bitcoin transaction graph processing code at [https://www.kaggle.com/code/clemwo/bitcoin-transactions-graph-neural-networks](https://www.kaggle.com/code/clemwo/bitcoin-transactions-graph-neural-networks), which significantly helped us with graph preprocessing steps in this project.

### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Note:** This project aims to enhance understanding of GNN performance in financial anomaly detection and provide insights into structural similarities between predicted illicit transaction networks.
