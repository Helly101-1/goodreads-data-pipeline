# Goodreads Review Prediction Pipeline 📚🔍

This project builds a scalable machine learning pipeline to analyze and predict Goodreads review sentiment using PySpark and cloud-based infrastructure.

## 📌 Objective

Predict whether a review is "liked" (rating ≥ 4) using:
- Review metadata: `n_votes`, `n_comments`, `review_text_length`
- Book features: `average_rating`
- Text features: TF-IDF on review text

## 🧰 Tools & Technologies

- **PySpark** (DataFrames, MLlib)
- **Google Cloud Platform** (GCS, Dataproc)
- **Python**, **Scikit-learn**, **Pandas**
- **Visualization:** Matplotlib, Seaborn

## 🔄 Pipeline Stages

1. **Data Acquisition**  
   - Downloaded 10GB+ JSON files of reviews & books  
   - Uploaded to GCS, stored in `/landing` and `/cleaned` buckets

2. **Data Cleaning & EDA**  
   - Explored 2.3M books and 5.2M reviews  
   - Cleaned duplicates, nulls, and joined on `book_id`

3. **Feature Engineering**  
   - Numerical: votes, comments, average_rating  
   - Textual: TF-IDF vectorization  
   - Combined features using `VectorAssembler`

4. **Modeling**  
   - Logistic Regression (binary classification)  
   - AUC: **0.54**, Accuracy: **~72%**  
   - Model output saved to GCS

5. **Visualization**  
   - Histograms, heatmaps, ROC curve  
   - Feature importance analysis

6. **Automation**  
   - Optional script to rerun data prep and refresh outputs

## 📈 Sample Visualizations

- Distribution of Ratings & Comments  
- Votes vs Review Rating  
- ROC Curve  
- Top 10 Most Rated Books  

## 📁 File Structure

/landing → raw data from GCS
/cleaned → cleaned parquet files
/trusted → final output used for modeling
/models → saved logistic regression model
/output → visualizations and evaluation metrics

## 👩‍💻 Project Outcome

This pipeline demonstrates how **user engagement (votes/comments)** impacts review sentiment and builds a foundation for **recommendation systems or review moderation** at scale.

## 🔗 Dataset Source

[UCSD Goodreads Dataset](https://cseweb.ucsd.edu/~jmcauley/datasets/goodreads.html)


---

