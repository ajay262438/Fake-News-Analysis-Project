# Fake-News-Analysis-Project
An AI system built with Python and LightGBM to detect fake news from text and live URLs, achieving 99.72% accuracy.

# AI-Powered Fake News Detection System

### Project for YBI Foundation Internship by Ajay

## 1. Project Overview

This project is an end-to-end machine learning system designed to detect fake news with high accuracy. The system analyzes the text content of a news article to determine its authenticity. It was further developed into a multi-modal tool that can scrape live news articles from URLs and check the credibility of the source domain, making it a practical tool for real-world use.

---

## 2. Features

* **High-Accuracy Text Classification**: Utilizes a LightGBM model to achieve **99.72% accuracy** on the test dataset.
* **Live URL Analysis**: Can fetch and analyze news articles directly from a web link.
* **Source Credibility Check**: Cross-references the news source against a list of known unreliable or satire websites.
* **Model Comparison**: Includes an evaluation of a baseline model (`PassiveAggressiveClassifier`) and the improved `LGBMClassifier`.

---

## 3. Technology Stack

* **Language**: Python 3
* **Libraries**:
    * Data Manipulation: Pandas
    * Machine Learning: Scikit-learn, LightGBM
    * NLP: NLTK
    * Web Scraping: Requests, BeautifulSoup
    * Utilities: TLDextract (for domain parsing)
* **Environment**: Google Colaboratory

---

## 4. Key Findings & Insights

While the model achieved an impressive accuracy of 99.72%, a critical insight was discovered during real-world testing. The model's performance is highly dependent on the similarity between the test data and its training data.

When tested on an article about a topic and region (Indian space technology) not present in its training data (primarily US politics), the model made an incorrect prediction. This demonstrates the "out-of-distribution" problem in AI and highlights the importance of training models on diverse datasets for robust real-world performance.

---

## 5. How to Use

The core of the system is a function that can take a URL as input and provide a two-level analysis:

1.  **Source Check**: Is the website on a known unreliable list?
2.  **Text Analysis**: Does the article's text resemble real or fake news?
