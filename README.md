# 🎵 Music Recommendation System: Item-Based Collaborative Filtering

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Latest-green.svg)](https://pandas.pydata.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Latest-orange.svg)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> 🎵 **A straightforward implementation of item-based collaborative filtering for music recommendation using Jaccard similarity. An educational project exploring the fundamentals of recommender systems with room for future improvements.**

## 📋 Table of Contents

- [🎯 Project Overview](#-project-overview)
- [✨ Key Features](#-key-features)
- [🏆 Performance Highlights](#-performance-highlights)
- [🛠️ Environment Setup](#️-environment-setup)
- [📊 Data Preparation](#-data-preparation)
- [🚀 Quick Start](#-quick-start)
- [📓 Notebook Overview](#-notebook-overview)
- [📈 Results & Analysis](#-results--analysis)
- [🔬 Technical Details](#-technical-details)
- [👥 Team](#-team)
- [📚 References](#-references)

---

## 🎯 Project Overview

This project implements a **basic item-based collaborative filtering system** for music recommendation as an educational exercise. Our system uses simple Jaccard similarity to identify songs with similar listening patterns, providing a foundation for understanding recommender systems fundamentals.

### 🎼 Why Music Recommendation?

Music recommendation presents interesting challenges for learning:
- **Large catalog**: 19,827+ unique songs creating sparsity issues
- **Subjective preferences**: Highly personal and varied taste
- **Cold start problem**: Many users have limited interaction history
- **Simple but effective**: Basic collaborative filtering can still produce reasonable results

### 🧠 Our Approach

We implemented a straightforward collaborative filtering system that:
- **Filters active users** (≥30 songs) to focus on users with sufficient data
- **Uses Jaccard similarity** as a simple but effective similarity measure
- **Evaluates performance** with standard precision-recall metrics
- **Demonstrates core concepts** while identifying areas for improvement

---

## ✨ Key Features

### 🎯 **Simple Data Filtering**
- User filtering strategy (≥30 songs per user)
- Focuses on users with sufficient interaction history
- Demonstrates the importance of data quality in recommendations

### 🔍 **Basic Similarity Computation**
- Jaccard similarity coefficient - simple but effective
- Co-occurrence matrix construction for item comparisons
- Straightforward recommendation ranking system

### 📊 **Educational Evaluation**
- Standard precision-recall analysis
- Performance comparison between filtered and unfiltered data
- Insights into the trade-offs of basic collaborative filtering

### 🚀 **Clean Implementation**
- Well-documented Python code for learning
- Modular structure for easy understanding
- Good foundation for exploring more advanced techniques

---

## 🏆 Performance Results

### 📊 **Our Findings**

| Metric | Unfiltered Data | **Filtered Data** | Improvement |
|--------|-----------------|-------------------|-------------|
| **Precision@10** | 8.4% | **11.6%** | +38% |
| **Recall@10** | 2.5% | **6.5%** | +160% |
| **Precision Range** | 0-12.5% | **2.5-15%** | More consistent |
| **Recall Range** | 0-2.5% | **1.5-6.5%** | 4.3x larger |

### 📈 **Context & Interpretation**

| Domain | Typical Precision@10 | Typical Recall@10 | **Our Results** |
|--------|---------------------|-------------------|-----------------|
| **Music** | 5-15% | 2-8% | **11.6% / 6.5%** |
| Movies | 10-25% | 5-15% | - |
| E-commerce | 15-30% | 8-20% | - |

> 📝 **Note**: Our results are within reasonable ranges for music recommendation, though there's significant room for improvement with more sophisticated algorithms.

---

## 🛠️ Environment Setup

### 📋 Prerequisites

- Python 3.8 or higher
- pip package manager
- Jupyter Notebook or JupyterLab

### 🔧 Installation Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/denda0duong/music-recsys
   cd RecSys/final
   ```

2. **Create Virtual Environment** (Recommended)
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

### 📦 Core Dependencies

```python
# Essential libraries
numpy>=1.21.0
pandas>=1.3.0
scikit-learn>=1.0.0
matplotlib>=3.5.0

# Data handling
pyarrow  # For parquet file support

# Jupyter environment
jupyter
ipython
```

---

## 📊 Data Preparation

### 📁 **Data Structure**

Your data should be organized as follows:
```
RecSys/final/
├── data/
│   └── user_track_df.parquet  # ✅ Already provided
├── item-similarity copy.ipynb
├── requirements.txt
└── README.md
```

### 🗂️ **Dataset Overview**

The `user_track_df.parquet` file contains:
- **983,357 users** with music listening history
- **19,827 unique songs** in the catalog
- **11,793,648 user-song interactions**
- **Columns**: `user_id`, `song_id`, `listen_count`, `popularity`

### 📈 **Data Characteristics**

| Statistic | Value |
|-----------|-------|
| **Users** | 983,357 |
| **Songs** | 19,827 |
| **Interactions** | 11,793,648 |
| **Sparsity** | 99.94% |
| **Avg Songs/User** | 11.4 |
| **Max Songs/User** | 548 |

> 📝 **Note**: The dataset is already preprocessed and ready to use. No additional data preparation steps required!

---

## 🚀 Quick Start

### ⚡ **Run the Complete Analysis**

1. **Open the Notebook**
   ```bash
   jupyter notebook "item-similarity copy.ipynb"
   ```

2. **Execute All Cells**
   - Click "Kernel" → "Restart & Run All"
   - Or press `Ctrl+A` then `Shift+Enter`

3. **View Results**
   - Performance metrics will be displayed
   - Precision-recall curves will be generated
   - Comprehensive analysis will be shown

### 🎯 **Key Outputs**

- **Recommendation Examples**: See personalized recommendations for sample users
- **Performance Metrics**: Precision-recall analysis for both filtered and unfiltered data
- **Visualization**: Interactive precision-recall curves
- **Timing Analysis**: Computational performance benchmarks

---

## 📓 Notebook Overview

### 🗂️ **Section-by-Section Guide**

#### **1. 📥 Data Loading and Preprocessing**
- Import essential libraries
- Load the parquet dataset
- Initial data exploration

#### **2. 🔍 Exploratory Data Analysis**
- Dataset statistics and characteristics
- User behavior patterns analysis
- Song popularity distribution
- Data quality assessment

#### **3. 🧹 Data Filtering and Preparation**
- Strategic user filtering (≥30 songs)
- Dataset transformation for collaborative filtering
- Performance impact analysis

#### **4. 🤖 Item-Based Collaborative Filtering Implementation**
- Complete recommender system class
- Jaccard similarity computation
- Co-occurrence matrix construction
- Recommendation generation pipeline

#### **5. 🎯 Model Training and Evaluation**
- Model instantiation and training
- Sample recommendation generation
- Performance validation

#### **6. 📊 Performance Analysis**
- Precision-recall calculation framework
- Comparative analysis (filtered vs unfiltered)
- Visualization and interpretation

#### **7. 🔬 Theoretical Framework and Discussion**
- Mathematical foundations
- Performance interpretation
- Industry benchmark comparison
- Future improvements and insights

---

## 📈 Results & Analysis

### 🎯 **Key Learnings**

1. **� Data Quality Matters**
   - Strategic user filtering improves recommendation quality
   - Simple preprocessing can have significant impact on results

2. **⚖️ Trade-offs in Collaborative Filtering**
   - Filtering removes 92.2% of users but retains 32.7% of interactions
   - Quality vs. quantity decisions are crucial in recommender systems

3. **🧮 Computational Considerations**
   - Basic algorithms can be computationally intensive
   - Matrix operations scale with user engagement levels
   - Simple doesn't always mean fast

4. **📈 Room for Improvement**
   - Results show the potential of collaborative filtering
   - Many advanced techniques could further improve performance
   - Hybrid approaches combining multiple methods show promise

### 🔮 **Future Improvements**

This basic implementation provides a foundation for exploring:
- **Advanced similarity measures** (cosine similarity, Pearson correlation)
- **Matrix factorization techniques** (SVD, NMF)
- **Deep learning approaches** (neural collaborative filtering)
- **Hybrid methods** combining collaborative and content-based filtering
- **Temporal modeling** for evolving user preferences

### 📊 **Performance Visualization**

The notebook generates comprehensive visualizations:
- **Precision-Recall Curves**: Compare filtered vs unfiltered performance
- **User Distribution Analysis**: Understand data characteristics
- **Timing Benchmarks**: Computational performance analysis

---

## 🔬 Technical Details

### 🧮 **Algorithm Overview**

Our implementation uses a straightforward approach:

1. **Data Preprocessing**
   - Filter users with ≥30 songs for sufficient interaction history
   - Create standard train/test splits (80/20)
   - Sample data for computational feasibility

2. **Similarity Computation**
   - Build co-occurrence matrices for user-item interactions
   - Calculate Jaccard similarity coefficients (simple but effective)
   - Apply basic weighted scoring for recommendations

3. **Recommendation Generation**
   - Rank items by similarity scores
   - Filter out already-listened songs
   - Return top-N recommendations

### 📐 **Mathematical Foundation**

We use basic but proven formulas:

**Jaccard Similarity:**
```
J(A,B) = |A ∩ B| / |A ∪ B|
```

**Recommendation Score:**
```
Score(song_i) = Σ(similarity_matrix[j,i]) / n
```

### 🚀 **Implementation Notes**

- **Set operations** for efficient intersection/union calculations
- **NumPy matrices** for numerical computations
- **Sampling strategies** to handle large datasets
- **Modular design** for easy understanding and extension

---

## 👥 Team

### 🎓 **Group Members**

- **20280054 - Tran Dang Khoa**
- **20280070 - Pham Tran Tan Phat**
- **22280006 - To Gia Bao**

### 🏫 **Academic Information**

- **Course**: Recommender Systems
- **Instructor**: Huynh Thanh Son
- **Institution**: University of Science HCMUS
- **Department**: Computer Science

---

## 📚 References

### 📖 **Key Literature**

1. **Sarwar, B., et al. (2001)**. Item-based collaborative filtering recommendation algorithms. *WWW Conference*.

2. **Su, X., & Khoshgoftaar, T. M. (2009)**. A survey of collaborative filtering techniques. *Advances in Artificial Intelligence*.

3. **Koren, Y., et al. (2009)**. Matrix factorization techniques for recommender systems. *Computer Magazine*.

### 🔗 **Additional Resources**

- [Collaborative Filtering Tutorial](https://developers.google.com/machine-learning/recommendation)
- [Music Recommendation Systems Survey](https://dl.acm.org/doi/10.1145/2827872)
- [Evaluation Metrics for Recommender Systems](https://link.springer.com/chapter/10.1007/978-0-387-85820-3_8)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🤝 Contributing

We welcome contributions! Please feel free to submit issues, feature requests, or pull requests.

---

## 🎉 Acknowledgments

- **University of Science HCMUS** for providing the academic framework
- **Professor Huynh Thanh Son** for guidance and support
- **Open-source community** for the amazing libraries and tools

---

<div align="center">

### 🌟 **Star this repository if you found it helpful!** 🌟

**Made with ❤️ by me**

</div>
