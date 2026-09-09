# Movie Industry — Exploratory Analysis and K-means Clustering

An exploratory data-analysis project in **R** examining movie financial and rating characteristics and using **K-means clustering** to identify interpretable movie profiles.

## Questions

- How are production budget, IMDb score, rating category, and gross revenue associated?
- Which genres have higher typical gross revenue?
- Can movies be grouped into interpretable financial/rating profiles using K-means?

## Methodology

The project combines:

- targeted data cleaning;
- exploratory visualization;
- genre-level summary statistics;
- log transformation of highly skewed financial variables;
- feature standardization;
- K-means clustering;
- elbow-based selection of the number of clusters;
- cluster profiling by budget, gross revenue, score, rating, and genre.

The elbow-selection rule rescales both `k` and within-cluster sum of squares (WSS) to `[0, 1]` and selects the point with the largest deviation from the straight line joining the endpoints. This makes the choice reproducible while remaining an exploratory heuristic rather than a formal proof of the correct number of clusters.

## Project structure

```text
.
├── movie_industry_clustering.ipynb
├── data/
│   └── README.md
└── README.md
```

## Data

The analysis uses Daniel Grijalva's **Movie Industry** dataset from Kaggle:

https://www.kaggle.com/datasets/danielgrijalvas/movies

The dataset itself is not redistributed in this repository. Download `movies.csv` from the source above and place it at:

```text
data/movies.csv
```

## Requirements

The notebook uses an **R Jupyter kernel** and `tidyverse`:

```r
install.packages("tidyverse")
```

## Interpretation

This is an **exploratory clustering analysis**, not a causal model and not a revenue-prediction model. Gross revenue is itself included as a clustering feature, so the clusters describe financial-performance profiles rather than predict future revenue.

Important limitations include sensitivity of K-means to feature choice and scaling, the loss of information from reducing ratings to `R` versus `non-R`, and the fact that financial values are not inflation-adjusted.
