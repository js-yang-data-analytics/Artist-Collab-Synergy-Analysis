# Artist-Collab-Synergy-Analysis
Recommending optimal K-pop artist collaborations using NLP(Sentiment Analysis) and Deep Learning.

# NLP-Based K-pop Artist Collaboration Synergy Recommendation for Advertising

Personal Project - Deriving data-driven marketing synergies by analyzing unstructured fandom discourse using Deep Learning and Natural Language Processing (NLP).

## 1. Project Overview

This project proposes a data-driven algorithm to recommend the most effective collaboration models (artists/celebrities) for advertising campaigns by analyzing public sentiment in unstructured text data.

### The Problem
* **Intuition-based Decisions:** Advertising collaboration choices currently rely heavily on planners' intuition or basic metrics like follower counts.
* **Risk of Negative Synergy:** High popularity does not always translate to positive synergy when two artists collaborate.

### Our Solution
We collect unstructured text data from the web, filter out noise using a Deep Learning-based sentiment classifier, and extract core entities using a Korean Morpheme Analyzer (KoNLPy) to find mathematically proven "Positive Synergy Pairs."

## 2. Project Pipeline & Methodology (End-to-End by Myself)

### Phase 1: Data Collection & Pipeline Construction
* **Data:** Crawled ~5,800 unstructured UGC (User Generated Content) texts from Naver News, Cafes, and Blogs using Naver OpenAPI.
* **Method:** Conducted data cleansing, handling missing values (NA), and noise reduction.

### Phase 2: Sentiment Classification (Deep Learning)
* **Method:** Trained a Deep Learning text classifier to label and filter the crawled data (0: Negative/Neutral, 1: Positive).
* **Output:** Selectively extracted sentences where the public reacted positively, minimizing the impact of negative issues or irrelevant noise.

### Phase 3: Morpheme Analysis & Co-occurrence Matrix
* **Method:** Evaluated various KoNLPy analyzers (Kkma, Komoran, Hannanum) and selected **'Hannanum'** for its superior noun-tagging accuracy.
* **Output:** Extracted proper nouns (celebrity names, brands) from the filtered positive texts to calculate co-occurrence frequencies.

## 3. Key Contributions (100% Solo Project)

* **End-to-End Data Pipeline:** Designed and implemented the entire flow from API crawling to final recommendation logic.
* **NLP Model Optimization:** Empirically tested and selected the best-performing morphological analyzer for Korean celebrity names.
* **Algorithm Design:** Translated a vague business problem ("Who should collaborate?") into a quantifiable NLP algorithm.

## 4. Analysis Results (Synergy Case Studies)

The algorithm successfully proved that optimal synergies are not always about putting the two most famous people together, but finding pairings with actual positive text-based correlations.

* **IVE (아이브) ➡️ Oh My Girl (오마이걸)** (35 Co-occurrences in positive contexts)
* **aespa Karina (에스파 카리나) ➡️ Lee Young-ji (이영지)** (78 Co-occurrences)
* **LE SSERAFIM Kim Chae-won (르세라핌 김채원) ➡️ Patricia (파트리샤)** (136 Co-occurrences)

*(Note: Replace the image link below with your actual result chart image)*
<!-- ![Result Image](insert_your_image_url_here) -->

## 5. Tech Stack

* **Programming:** Python
* **Data Collection:** Naver OpenAPI, BeautifulSoup
* **NLP & Deep Learning:** KoNLPy (Hannanum), Scikit-learn, Transformers (DL Text Classifier)
* **Data Handling:** Pandas, NumPy
