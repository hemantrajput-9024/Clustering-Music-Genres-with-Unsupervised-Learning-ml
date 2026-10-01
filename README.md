# 🎵 Clustering Music Genres with Machine Learning

## 📌 Project Overview

This project uses Machine Learning to group songs into different music segments based on their audio characteristics. The main purpose of the project is to identify groups of songs that have similar musical properties.

The dataset contains **1,994 songs** with information about artists, genres, release years, and different audio features such as BPM, Energy, Danceability, Loudness, Liveness, Valence, Acousticness, Speechiness, and Popularity.

The project uses **K-Means Clustering** to create music segments and then uses a **Random Forest Classifier** to predict the generated cluster labels.

---

## 🎯 Objectives

* Analyze a music dataset.
* Perform basic data cleaning and exploration.
* Check missing values and duplicate records.
* Select relevant numerical audio features.
* Apply feature scaling.
* Group songs using K-Means Clustering.
* Visualize the generated music clusters.
* Use Random Forest to predict cluster labels.
* Evaluate the classification performance.
* Save and load the trained Random Forest model using Joblib.

---

## 📊 Dataset

The dataset contains **1,994 rows and 15 columns** before preprocessing.

Important columns include:

* `Title`
* `Artist`
* `Top Genre`
* `Year`
* `Beats Per Minute (BPM)`
* `Energy`
* `Danceability`
* `Loudness (dB)`
* `Liveness`
* `Valence`
* `Length (Duration)`
* `Acousticness`
* `Speechiness`
* `Popularity`

The `Index` column is removed during preprocessing because it is not required for the clustering analysis.

---

## 🔍 Data Preprocessing

The following preprocessing steps were performed:

1. The dataset was loaded using Pandas.
2. The structure of the dataset was inspected.
3. Missing values were checked.
4. Duplicate records were checked.
5. Descriptive statistics were generated.
6. The unnecessary `Index` column was removed.
7. Numerical audio features were selected for Machine Learning.

The dataset contained **no missing values** and **no duplicate rows** according to the notebook checks.

---

## 🤖 Machine Learning Approach

### 1. K-Means Clustering

K-Means is an unsupervised Machine Learning algorithm used to divide data into groups based on similarity.

In this project, K-Means was used with:

```python
n_clusters = 10
```

The generated cluster labels were stored in a new column called:

```text
Music Segments
```

The numerical cluster labels were converted into readable labels such as:

```text
Cluster 1
Cluster 2
Cluster 3
...
Cluster 10
```

This allows songs with similar audio characteristics to be grouped into different music segments.

---

## 📈 Features Used for Classification

The Random Forest model uses the following audio features:

* Beats Per Minute (BPM)
* Loudness (dB)
* Liveness
* Valence
* Acousticness
* Speechiness

These features are scaled using `MinMaxScaler` before training the classifier.

---

## 🌳 Random Forest Classification

After creating clusters using K-Means, a Random Forest Classifier was trained to predict the generated cluster labels.

The data was divided into:

* **80% Training Data**
* **20% Testing Data**

The Random Forest model was trained using the scaled features.

```python
RandomForestClassifier(random_state=42)
```

---

## 📊 Model Performance

The Random Forest model achieved:

### Accuracy: **95.49%**

The classification report was also generated using:

* Precision
* Recall
* F1-score
* Support

The test set contained **399 records**. The reported macro average was approximately **0.96 precision, 0.94 recall, and 0.95 F1-score**.

---

## 📊 Visualization

An interactive **3D scatter plot** was created using Plotly.

The visualization uses:

* **X-axis:** Beats Per Minute (BPM)
* **Y-axis:** Energy
* **Z-axis:** Danceability

Different music segments are displayed separately so that the distribution of the generated clusters can be explored visually.

---

## 💾 Model Saving and Loading

The trained Random Forest model is saved using Joblib:

```python
joblib.dump(clf, "cluster_random_forest.pkl")
```

The saved model can later be loaded using:

```python
loaded_model = joblib.load("cluster_random_forest.pkl")
```

The loaded model produced the same **95.49% accuracy** on the test data.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Plotly
* Joblib
* Google Colab / Jupyter Notebook

---

## 📁 Project Structure

```text
Music-Genre-Clustering/
│
├── Clustering_Music_Genres_with_Machine_Learning.ipynb
├── archive.zip
├── cluster_random_forest.pkl
└── README.md
```

---

## 🚀 Project Workflow

```text
Dataset
   ↓
Data Loading
   ↓
Data Inspection
   ↓
Missing Value Check
   ↓
Duplicate Check
   ↓
Data Preprocessing
   ↓
Feature Selection
   ↓
Feature Scaling
   ↓
K-Means Clustering
   ↓
Music Segments
   ↓
3D Visualization
   ↓
Random Forest Classification
   ↓
Model Evaluation
   ↓
Save Model using Joblib
```

---

## ✅ Conclusion

This project demonstrates how Machine Learning can be used to discover patterns in music data. K-Means clustering creates different music segments based on audio characteristics, while Random Forest is used to predict those generated segments.

The Random Forest classifier achieved **95.49% accuracy** on the test set, showing that the selected audio features can effectively distinguish between the clusters generated in this project.

---

## 👨‍💻 Author

**Hemant Singh**

BCA – Machine Learning / Data Science Project
