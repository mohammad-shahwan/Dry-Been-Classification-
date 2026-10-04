# Dry Bean Classification

A machine learning project for classifying 7 varieties of dry beans using morphological features. The repository compares several supervised classification models and evaluates clustering methods to understand both predictive performance and the separability of bean classes.

## Project goal

This project aims to:

- classify dry bean varieties from their physical measurements
- benchmark multiple classification algorithms
- compare model performance using standard metrics
- explore unsupervised clustering behavior on the same dataset

The best-performing model in this project achieves approximately 93% accuracy, with strong precision, recall, and F1 scores across the 7 classes.

## Dataset

The project uses the dry bean dataset stored in:

- `Dry_Bean_Dataset.xlsx`

This dataset contains morphological attributes for different dry bean varieties, including features such as shape, area, perimeter, compactness, and aspect ratio. The target variable is the bean type/class label.

## Repository contents

- `Classifying DM.ipynb` — full exploratory data analysis, preprocessing, model training, and evaluation workflow
- `Dry_Bean_Dataset.xlsx` — raw dataset used for modeling
- `classification_clustering_results.csv` — summarized results for the tested classification and clustering methods
- `README.md` — project overview and usage instructions

## Models evaluated

The notebook benchmarks multiple supervised learning models, including:

- Logistic Regression
- Random Forest
- XGBoost
- K-Nearest Neighbors (KNN)

It also evaluates unsupervised clustering techniques:

- K-Means
- Hierarchical Clustering
- DBSCAN

## Performance summary

The classification models were evaluated using accuracy, precision, recall, and F1-score.

| Model | Type | Accuracy | Precision | Recall | F1-Score |
| --- | --- | ---: | ---: | ---: | ---: |
| Logistic Regression | Classification | 0.9266 | 0.9393 | 0.9369 | 0.9379 |
| Random Forest | Classification | 0.9254 | 0.9382 | 0.9347 | 0.9364 |
| XGBoost | Classification | 0.9243 | 0.9391 | 0.9358 | 0.9373 |
| KNN | Classification | 0.9232 | 0.9395 | 0.9344 | 0.9367 |

These results show strong predictive performance across all tested classification models, with Logistic Regression performing best in this comparison.

## Clustering results

The clustering analysis provides insight into how well unsupervised algorithms separate bean varieties without using the labels during training:

- K-Means: silhouette score ~0.309
- Hierarchical Clustering: silhouette score ~0.279
- DBSCAN: poor separation in this setup (silhouette near zero / negative)

This indicates that while the data is highly learnable with supervised models, the clustering structure is more challenging when labels are not used.

## Environment setup

This project uses Python and common data science libraries.

### Prerequisites

- Python 3.9+
- Jupyter Notebook or Jupyter Lab
- pip

### Install dependencies

```bash
pip install pandas numpy scikit-learn xgboost matplotlib seaborn openpyxl jupyter
```

## Run the project

1. Clone the repository:

```bash
git clone https://github.com/mohammad-shahwan/Dry-Been-Classification-.git
cd Dry-Been-Classification-
```

2. Open the notebook:

```bash
jupyter notebook "Classifying DM.ipynb"
```

3. Run the cells in order to:
   - load the dataset
   - preprocess features
   - train the models
   - compare performance metrics
   - inspect clustering outputs

## Key takeaways

- Machine learning can classify dry bean varieties with high accuracy using morphology-based features.
- The project demonstrates a complete end-to-end workflow from dataset exploration to model comparison.
- Supervised learning is substantially more effective than unsupervised clustering for this problem in the tested setup.

## Notes

This repository is designed as an educational and applied data science project. It is useful for learning model comparison, evaluation metrics, and clustering behavior on a real-world tabular dataset.

## Contact / contribution

If you want to improve the notebook, add more models, or expand the analysis, feel free to open a pull request or contribute additional experiments.
