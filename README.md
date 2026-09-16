# 📩 SMS Spam Detection using Naive Bayes & TF-IDF

A Machine Learning project designed to filter SMS messages into **Ham** (Legitimate) or **Spam** using Natural Language Processing (NLP) techniques and a **Multinomial Naive Bayes** classifier.

---

## 📌 Project Overview
This repository implements an end-to-end NLP pipeline to classify imbalanced SMS text data. It handles text noise, normalizes linguistic structures, extracts key TF-IDF features, and evaluates classification performance using standard ML metrics.

* **Dataset Size:** 5,572 text messages (Kaggle SMS Spam Collection)
* **Target Classes:** 
  * `Ham`: ~86.6% (4,825 messages)
  * `Spam`: ~13.4% (747 messages)
* **Overall Accuracy:** ~97.3%

---

## 🛠️ Data Preprocessing & Methodology

### 1. Text Cleaning & Normalization
* **Encoding:** Used `latin-1` to correctly handle currency symbols (£) and special characters without encoding crashes.
* **Regex Cleaning:** Lowercased all text and removed non-alphabetic characters/punctuation (`[^a-z\s]`).
* **Tokenization & Stopwords:** Tokenized messages using NLTK and removed common English stop words.
* **Lemmatization:** Used WordNet Lemmatizer to reduce words to their base dictionary forms.

### 2. Feature Extraction
* **TF-IDF Vectorization:** Extracted the top 5,000 features (`max_features=5000`) based on term frequency-inverse document frequency weighting.

### 3. Model Training
* **Algorithm:** Multinomial Naive Bayes (`MultinomialNB`).
* **Data Split:** 80% Training / 20% Testing (`random_state=42`).

---

## 📊 Performance & Results

* **Overall Accuracy:** `97.3%`
* **Confusion Matrix:** Low rate of false positives (ensuring safe handling of legitimate messages).

| Class | Precision | Recall | F1-Score | Support |
| :--- | :---: | :---: | :---: | :---: |
| **Ham** | 0.97 | 1.00 | 0.98 | 965 |
| **Spam** | 1.00 | 0.80 | 0.89 | 150 |

---

## 📂 Repository Structure

```text
├── spam.csv                 # SMS Dataset
├── SMS_Spam_Detection.ipynb # Jupyter Notebook with data processing & model training
├── SMS_Spam_Detection.pptx  # Project presentation slides
└── README.md                # Project documentation
