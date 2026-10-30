# Automobile Segmentation with Hierarchical Clustering

## Project overview
This project uses unsupervised machine learning to group 32 automobile models using 11 numeric vehicle characteristics from the classic `mtcars` dataset.

The notebook demonstrates:
- Data inspection and quality checks
- Feature selection and standardization
- Average-linkage and Ward hierarchical clustering
- Dendrogram visualization
- Silhouette-score comparison for candidate cluster counts
- Cluster profiling and PCA visualization
- Findings, limitations, and recommended next steps

## Main analytical question
Can automobile models be grouped into interpretable segments based on fuel economy, engine, transmission, gearing, and vehicle characteristics?

## Repository contents
- `Automobile_Hierarchical_Clustering.ipynb` — complete analysis notebook
- `requirements.txt` — Python dependencies
- `mtcars.csv` — required input dataset (not included in this upload)

## Run the notebook
1. Download the `mtcars` dataset as a CSV with a `model` column and the 11 numeric feature columns.
2. Save the file as `mtcars.csv` in this same folder.
3. Install dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

4. Launch Jupyter and run all notebook cells:

   ```bash
   jupyter notebook
   ```

## Important interpretation notes
The worked example selects Ward linkage with three clusters as a practical balance of separation, cluster size, and interpretability. This is an exploratory demonstration using a small historical dataset; it should not be generalized to today's automobile market. Cluster labels are descriptive, not causal or externally validated.

## Tools
Python, pandas, NumPy, Matplotlib, Seaborn, SciPy, scikit-learn, and Jupyter Notebook.
