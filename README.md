# Dream Clustering — Unsupervised NLP on Personal Dream Reports

This project explores unsupervised machine learning techniques to discover emergent patterns and themes in dream narratives. Using a dataset of dream reports (from DreamBank), I aim to cluster dreams into meaningful groups based on textual content.

---

## Project Goals

-  **Preprocess** raw dream text into structured, clean data
-  **Vectorize** dreams using TF-IDF and/or sentence embeddings
-  **Cluster** dreams using KMeans, DBSCAN, or hierarchical methods
-  **Interpret** and name clusters based on top keywords and patterns
-  **Visualize** dream clusters using 2D projection techniques
-  **Report** findings in a clear, research-style writeup

---

##  Project Structure
```
dream-clustering-ml/
├── data/ # Raw and processed dream data
│ ├── raw/ # Original dream JSONs or CSVs
│ └── processed/ # Cleaned text, vectors, cluster labels
│
├── notebooks/ # Development notebooks
│ ├── 01-data-cleaning.ipynb
│ ├── 02-feature-extraction.ipynb
│ ├── 03-clustering.ipynb
│ ├── 04-visualisation.ipynb
│ └── 05-report-figures.ipynb
│
├── report/ # Project report in progress
│ ├── draft.md
│ └── final_report.pdf
│
├── utils/ # Utility functions 
│
├── LICENSE # MIT
├── README.md # You Are Here
└── requirements.txt
```
---

##  Data Source

Dreams are sourced from [DreamBank](http://www.dreambank.net/) — a public research dataset of dream reports from multiple individuals across demographics.

---

##  Tools & Libraries

- Python 3.10+
- `pandas`, `numpy`
- `nltk` / `spaCy`
- `matplotlib`, `seaborn`, `wordcloud`, `UMAP`
- ...


##  Current Status

- [x] Collecting raw data from dream collections
- [x] Text cleaning and preprocessing
- [ ] Vectorization + dimensionality reduction
- [ ] Clustering and interpretation
- [ ] Visualizations and final writeup
