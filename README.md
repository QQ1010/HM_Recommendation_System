# H&M Recommendation System

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