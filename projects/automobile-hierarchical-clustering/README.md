# Automobile Segmentation with Hierarchical Clustering

> **Unsupervised machine learning | Python | 32 automobile models | 11 numeric features**

## Executive summary
This project explores whether automobiles can be grouped into meaningful segments using fuel economy, engine, transmission, gearing, and vehicle characteristics. I built a reproducible hierarchical-clustering workflow, compared Average and Ward linkage, evaluated candidate cluster counts with silhouette scores, profiled the resulting groups, and visualized the data with PCA.

**The worked solution uses Ward linkage with three clusters**, selected as a practical balance of separation, cluster size, and interpretability—not as a claim that three clusters are the only mathematically optimal answer.

## Business question
Can automobile models be grouped into interpretable segments based on their technical specifications, and what characteristics distinguish those groups?

## Project files
| File | Purpose |
|---|---|
| [Analysis notebook](Automobile_Hierarchical_Clustering.ipynb) | End-to-end analysis, code, charts, interpretation, and limitations |
| [Dataset](mtcars.csv) | 32 automobile observations and 11 numeric variables |
| [Dependencies](requirements.txt) | Python packages needed to run the analysis |

## Methodology
1. **Inspect the data** — review dimensions, data types, missing values, duplicates, and descriptive statistics.
2. **Prepare features** — exclude the vehicle identifier and standardize the 11 numeric variables.
3. **Build hierarchical models** — compare Average and Ward linkage using Euclidean distance.
4. **Evaluate cluster counts** — examine silhouette scores and cluster sizes for candidate solutions from 2 to 7 groups.
5. **Interpret segments** — summarize original feature values by cluster and inspect vehicle membership.
6. **Visualize** — use dendrograms, a standardized cluster-profile heatmap, and a two-component PCA projection.

## Key findings in the worked three-cluster solution
- **Cluster 1 (15 models):** higher average fuel economy and lower average weight and horsepower than the other groups.
- **Cluster 2 (12 models):** heavier vehicles; all have eight cylinders in this sample, with lower average fuel economy.
- **Cluster 3 (5 models):** relatively high average horsepower and lower average weight than Cluster 2.

These are descriptive patterns in a small historical sample. They do not establish causation or represent validated current-market customer segments.

## Tools and skills demonstrated
Python, pandas, NumPy, Matplotlib, Seaborn, SciPy, scikit-learn, data quality assessment, feature scaling, hierarchical clustering, model evaluation, cluster profiling, PCA, data visualization, and analytical communication.

## Run it locally
From this directory:

```bash
python -m pip install -r requirements.txt
jupyter notebook Automobile_Hierarchical_Clustering.ipynb
```

Run the notebook cells from top to bottom. The notebook reads `mtcars.csv` from the same directory.

## Dataset and attribution
The included CSV is the classic `mtcars` automobile dataset, sourced from the Plotly datasets repository: [plotly/datasets — mtcars.csv](https://github.com/plotly/datasets/blob/master/mtcars.csv). The data represents a small historical sample and is commonly used for statistical and machine-learning demonstrations.

## Limitations and responsible interpretation
- The sample contains only 32 historical automobile models.
- Standardizing all variables gives each feature unit variance; it does not prove equal business importance.
- The `vs` and `am` fields are binary-coded and their use with Euclidean distance is a modeling choice.
- Cluster-count selection is sensitive to the features, distance measure, linkage, and intended use.
- There is no external ground-truth segmentation or independent validation set.

**Next steps:** test alternative feature sets and distance choices, assess cluster stability, and use a larger contemporary dataset with price, sales, customer, and geographic variables before making commercial decisions.
