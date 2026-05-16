# Artist-Collab-Synergy-Analysis
Recommending optimal K-pop artist collaborations using NLP(Sentiment Analysis) and Deep Learning.

# NLP-Based Advertising Collaboration Synergy Recommendation

Personal Project - Deriving data-driven marketing synergies by analyzing unstructured public discourse using Deep Learning and Natural Language Processing (NLP).

## 1. Project Overview

This project proposes a data-driven algorithm to recommend the most effective collaboration models (celebrities/artists) for advertisement

### The Problem
* **Intuition-based Decisions:** Selecting advertising models currently relies heavily on planners' intuition or basic metrics like follower counts.
* **Maximizing ROI:** How can we maximize the positive advertising effect (brand image, user growth, stock price) with the same marketing budget? 

### Solution
Instead of guessing, we collect unstructured text data from the web, filter out noise using a Deep Learning-based sentiment classifier, and extract core entities using a Korean Morpheme Analyzer (KoNLPy) to find mathematically proven "Positive Synergy Pairs."

## 2. Project Pipeline & Methodology (End-to-End by Myself)

**Step 1: Data Collection**
* Crawled unstructured UGC (User Generated Content) texts from Naver News, Cafes, and Blogs using Naver OpenAPI.

**Step 2 & 3: Deep Learning Sentiment Classification**
* Preprocessed data (NA removal, positive/negative labeling).
* Trained a Deep Learning text classifier (split into Train/Test sets) to evaluate training and validation loss.

**Step 4: Filtering Positive Discourse**
* Applied the trained model to new target data (e.g., Jang Won-young, Karina).
* Selectively extracted only the sentences where the public reacted **positively (LABEL_1)**, minimizing the impact of negative issues or irrelevant noise.

**Step 5 & 6: Morpheme Analysis & Co-occurrence Extraction**
* Evaluated various KoNLPy analyzers (Kkma, Komoran, Hannanum) and selected **'Hannanum'** for its superior noun-tagging accuracy for Korean names.
* Extracted proper nouns from the filtered positive texts to calculate co-occurrence frequencies and identify the most frequently mentioned collaborative figures.

## 3. Analysis Results (Synergy Case Studies)

The algorithm successfully proved that optimal synergies are not always about putting the two most famous people together, but finding pairings with actual positive text-based correlations.

* **IVE (아이브) ➡️ Oh My Girl (오마이걸)** (35 Co-occurrences in positive contexts)
* **aespa Karina (에스파 카리나) ➡️ Lee Young-ji (이영지)** (78 Co-occurrences)
* **LE SSERAFIM Kim Chae-won (르세라핌 김채원) ➡️ Patricia (파트리샤)** (136 Co-occurrences)

<img width="1270" height="591" alt="image" src="https://github.com/user-attachments/assets/3eb22450-46e2-41cc-8dc7-8cf275e83083" />
<img width="1253" height="592" alt="image" src="https://github.com/user-attachments/assets/27be18c5-e659-49ea-a010-88e4e889c849" />
<img width="1269" height="584" alt="image" src="https://github.com/user-attachments/assets/8640bf36-85e5-486f-b6b7-4a14bce96ebb" />


## 4. Limitations & Lessons Learned

### Business Limitations
* **Cost Variables:** The current algorithm does not factor in the actual casting cost (budget constraints) of different artists.
* **Post-Campaign Verification:** The project lacks a causal impact analysis to verify the actual advertising ROI after a recommended collaboration takes place.

### Significance & Lessons Learned
Despite these business limitations, the greatest takeaway from this project is the experience of establishing a strong foundation for **Data-driven Problem Solving**. 

* **Defining the Problem:** I successfully translated a vague, intuition-based business problem into a clearly defined analytical task.
* **Logical Pipeline Design:** By systematically designing and implementing a step-by-step approach (Data Collection ➡️ Sentiment Classification ➡️ NLP Morpheme Analysis) in Python, I was able to validate the initial hypothesis.
* **Core Insight:** This end-to-end process taught me that data science is not just about building complex models, but understanding *why* each analytical step is necessary and *how* the data connects to solving the actual core problem.


## 5. Tech Stack

* **Programming:** Python
* **Data Collection:** Naver OpenAPI
* **NLP & Deep Learning:** KoNLPy (Hannanum, Kkma, Komoran), Transformers (DL Text Classifier)
* **Data Handling:** Pandas, NumPy
