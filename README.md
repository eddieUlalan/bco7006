# BCO7006 – Assessment 4: Case 3  
## Sentiment Analysis Using Bag of Words and Machine Learning

**Course:** Coding For Business Analytics (BCO7006) — Victoria University  
**Assessment:** Business Analytics Solution Modelling: Research Report (Group)  
**Case Study:** Bag of Words Meets Bags of Popcorn  

---

## Project Overview

With the increasing amount of customer feedback available online, businesses need effective ways to understand customer opinions quickly and at scale. Sentiment analysis provides a way to automatically classify text data and identify whether feedback is positive or negative.

This project explores a movie review sentiment classification problem based on the Kaggle competition **"Bag of Words Meets Bags of Popcorn"**. The original notebook provided for this case was analysed, reproduced, and improved by applying a more advanced natural language processing approach.

The goal of this project is not only to build an accurate prediction model, but also to demonstrate how different modelling decisions can affect business analytics outcomes.

| Item | Details |
|---|---|
| Competition | Bag of Words Meets Bags of Popcorn |
| Original Notebook Analysed | rochachan – Part 1 for Beginners: Bag of Words |
| Dataset | NLTK Movie Reviews Dataset (2,000 labelled IMDB reviews) |
| Programming Language | Python 3.10+ |
| Development Environment | Google Colab / Jupyter Notebook |

---

## Getting Started

The notebook has been designed to run easily in Google Colab without requiring additional setup.

### Running the Notebook

1. Open Google Colab
2. Upload `assessment4_case3.ipynb`
3. Select **Runtime → Run All**
4. Required libraries and datasets will be automatically installed

---

## Notebook Workflow

The analysis is organised into seven sections, following a complete business analytics workflow from data preparation through to model evaluation.

### Part 1 — Environment Setup

The first section prepares the working environment by installing and importing the required Python libraries.

These libraries support:
- Data processing
- Natural language processing
- Machine learning
- Visualisation

---

### Part 2 — Data Preparation

The dataset is loaded and transformed into a structured format suitable for analysis.

Each review contains:
- **Review text** — the customer's written opinion
- **Sentiment label** — positive (1) or negative (0)

Basic checks are performed to understand the dataset structure and ensure there are no missing values affecting the analysis.

---

### Part 3 — Reviewing the Original Approach

The original Kaggle notebook was recreated to understand its modelling process.

The original workflow includes:

- Cleaning review text by removing HTML tags and unnecessary characters
- Converting text into numerical features using CountVectorizer
- Training a Random Forest classification model
- Evaluating sentiment prediction performance

This provides a baseline model that can be compared against the improved approach.

---

### Part 4 — Exploring the Data

Before improving the model, exploratory data analysis was conducted to better understand the dataset.

The analysis includes:
- Sentiment distribution
- Review length comparison between positive and negative reviews
- Word frequency patterns through word clouds

These visualisations help identify patterns within customer opinions.

---

### Part 5 — Areas for Improvement

Although the original model provides reasonable results, several opportunities were identified to improve performance:

| Issue | Business Impact | Improvement |
|---|---|---|
| CountVectorizer treats all words equally | Common words may introduce unnecessary noise | Use TF-IDF weighting |
| Only individual words are considered | Important phrases may be missed | Include word combinations (bigrams) |
| Random Forest provides limited explanation | Difficult to understand prediction reasons | Use Logistic Regression coefficients |
| Single train/test split | Results may vary depending on data split | Apply cross-validation |

---

### Part 6 — Improved Sentiment Model

The improved approach focuses on creating a more reliable and interpretable model.

The following improvements were introduced:

- **Porter Stemmer**  
  Reduces different word forms into a common root, improving feature consistency.

- **TF-IDF Vectorisation**  
  Gives greater importance to meaningful words while reducing the impact of very common terms.

- **Bigram Features**  
  Captures short phrases such as "not good" that provide stronger sentiment meaning than individual words.

- **Logistic Regression Model**  
  Provides strong classification performance while allowing better understanding of which words influence predictions.

- **5-Fold Cross Validation**  
  Provides a more reliable estimate of model performance.

---

### Part 7 — Model Evaluation

The original and improved approaches are compared using multiple evaluation methods:

- Accuracy comparison
- ROC-AUC evaluation
- Confusion matrices
- ROC curves
- Important positive and negative sentiment features
- Example predictions using new reviews

---

## References

- Kaggle. (2014). *Bag of Words Meets Bags of Popcorn.*
- rochachan. (2022). *Part 1 for Beginners — Bag of Words.*
- Pedregosa et al. (2011). *Scikit-learn: Machine Learning in Python.*
- Bird, Klein & Loper (2009). *Natural Language Processing with Python.*
