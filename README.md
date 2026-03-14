# Clustering

# 🛍️ Mall Customer Segmentation

Unsupervised machine learning project that segments mall customers based on their **Annual Income** and **Spending Score** using two clustering approaches — **K-Means** and **Hierarchical (Agglomerative) Clustering**.

---

## 📌 Problem Statement

Retail businesses need to understand their customers to design targeted marketing strategies. This project groups mall customers into distinct segments so that the business can identify, for example, high-income/high-spending "VIP" customers vs. low-income/low-spending ones — enabling personalised outreach for each group.

---

## 📂 Project Structure

```
├── Mall_Customers.csv              # Dataset
├── k_means_clustering.ipynb        # K-Means Clustering notebook
├── hierarchical_clustering.ipynb   # Hierarchical Clustering notebook
└── README.md
```

---

## 📊 Dataset

**File:** `Mall_Customers.csv`  
**Source:** [Kaggle – Mall Customers Dataset](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)

| Column | Description |
|---|---|
| `CustomerID` | Unique customer identifier |
| `Genre` | Gender of the customer |
| `Age` | Age of the customer |
| `Annual Income (k$)` | Annual income in thousands of dollars |
| `Spending Score (1-100)` | Score assigned by the mall based on spending behaviour |

> **Features used for clustering:** `Annual Income (k$)` and `Spending Score (1-100)`

---

## 🤖 Methods

### 1. K-Means Clustering (`k_means_clustering.ipynb`)

- Uses the **Elbow Method** (WCSS plot) to determine the optimal number of clusters → **5 clusters**
- Initialisation strategy: `k-means++` for better convergence
- Visualises clusters with distinct colours and marks centroids

**The 5 Customer Segments:**

| Cluster | Annual Income | Spending Score | Profile |
|---|---|---|---|
| 1 | Low | Low | Budget-conscious customers |
| 2 | Low | High | Impulsive spenders |
| 3 | Medium | Medium | Average customers |
| 4 | High | Low | Careful high-earners |
| 5 | High | High | Target / VIP customers |

---

### 2. Hierarchical Clustering (`hierarchical_clustering.ipynb`)

- Builds a **Dendrogram** using Ward's linkage and Euclidean distance to determine the optimal number of clusters → **3 clusters**
- Uses `AgglomerativeClustering` from scikit-learn
- Provides a broader, top-level segmentation of the customer base

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data loading and manipulation |
| `numpy` | Numerical operations |
| `matplotlib` | Plotting clusters, elbow curve, dendrogram |
| `seaborn` | Styled elbow method visualisation |
| `scikit-learn` | KMeans & AgglomerativeClustering |
| `scipy` | Dendrogram generation |

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/your-username/mall-customer-segmentation.git
cd mall-customer-segmentation
```

### 2. Install dependencies
```bash
pip install numpy pandas matplotlib seaborn scikit-learn scipy
```

### 3. Run the notebooks

Launch Jupyter and open either notebook:
```bash
jupyter notebook
```
- `k_means_clustering.ipynb` — K-Means approach with 5 clusters
- `hierarchical_clustering.ipynb` — Hierarchical approach with 3 clusters

Make sure `Mall_Customers.csv` is in the same directory as the notebooks.

---

## 📈 Results

### Elbow Method (K-Means)
The WCSS curve shows a clear elbow at **k = 5**, confirming 5 as the optimal cluster count.

### Dendrogram (Hierarchical)
The Ward linkage dendrogram shows the largest vertical gap at **3 clusters**, making it the optimal cut point.

---

## 💡 Key Takeaways

- **K-Means** gives a more granular 5-segment view, ideal for fine-tuned marketing campaigns.
- **Hierarchical Clustering** gives a broader 3-segment overview, useful for high-level strategic decisions.
- Both methods agree that **high income + high spending score** customers are a distinct and valuable group worth targeting.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
