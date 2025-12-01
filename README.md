# H&M Recommendation System
## 📌 Description
This project implements a personalized fashion recommendation system for the
H&M Personalized Fashion Recommendations Kaggle competition.

📌 Competition page:
https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations

In this competition, the goal is to predict **the next 12 items a customer is likely to purchase**,
based on two years of transaction logs, customer metadata, and article (product) metadata.

The evaluation metric is **MAP@12 (Mean Average Precision at 12)**,
which rewards both ranking quality and correct ordering of recommended items.

This project follows the commonly adopted **two-stage recommendation pipeline**:

1. **Candidate Generation (Recall)**
- Popularity-based recall
- User-history-based recall
- Time-aware recall (recent trending items)
These methods efficiently narrow down the millions of possible items to a manageable set.

2. **Ranking Model**
A machine-learning ranker (LightGBM / neural embeddings) is trained to score and sort the recalled candidates
using features derived from:
- Customer attributes
- Product metadata (categories, garment groups, etc.)
- Transaction history
- Temporal patterns (recency, seasonality, time decay)
The final output is a personalized list of 12 recommended items for each customer.

This repository contains:
- Data preprocessing scripts
- Exploratory Data Analysis (EDA)
- Candidate generation methods
- Ranking model implementation
- Final solution pipeline

## 📌 Environment
```
> conda create -n hm_rec python=3.10 -y
> conda activate hm_rec
> pip install -r requirements.txt
```

📢 Notes
Setup `~/.kaggle/kaggle.json` (if downloading kaggle datasets fails)
1. Kaggle → Account
2. API → Create New API Token
3. Download `kaggle.json`
4. put the file to `~/.kaggle/kaggle.json`
5. `chmod 600 ~/.kaggle/kaggle.json`

## 📌 Dataset Download
### Download all datasets (take 10+ hours)
```
> kaggle competitions download -c h-and-m-personalized-fashion-recommendations
> unzip h-and-m-personalized-fashion-recommendations.zip -d hm_data
```

### Download dataset without images (👍🏻 Recommend)
```
> kaggle competitions download -c h-and-m-personalized-fashion-recommendations -f sample_submission.csv
> unzip -o sample_submission.csv
> kaggle competitions download -c h-and-m-personalized-fashion-recommendations -f articles.csv
> unzip -o articles.csv
> kaggle competitions download -c h-and-m-personalized-fashion-recommendations -f customers.csv
> unzip -o customers.csv
> kaggle competitions download -c h-and-m-personalized-fashion-recommendations -f transactions_train.csv
> unzip -o transactions_train.csv
```