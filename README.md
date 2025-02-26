# Amazon-book-recommender-system

---

This project includes a basic implementation of Amazon book recommender system and a report including future enhancements and some analysis of other recommender systems

---

## 📚 Basic Implementation Book Recommendation System
A Hybrid Book Recommendation System leveraging Collaborative Filtering (Item-CF, User-CF), Popularity-Based, Location-Based Preferences to provide personalized and cold-start recommendations.

---

## 📌 Features 

✔ Hybrid Recommendation: Combines Item-Based Collaborative Filtering (Item-CF) with popularity and location-based methods.
✔ Cold-Start Strategy: Uses 60% globally popular books and 40% regionally preferred books for new users.
✔ Scalability: Efficiently computes book recommendations using CSR sparse matrix storage and precomputed item-item similarity.
✔ Performance Optimization: Item-CF outperforms User-CF

---

## 📂 Dataset

The dataset consists of:

User Ratings: Book reviews, ratings (1-10), and timestamps.
Book Metadata: ISBN, title, author, year of publication, and publisher.
User Demographics: Age, location (country).

---

## 🔧 How It Works

### 1. Data Preprocessing
Missing Values: Imputes missing ages using the median.
Data Cleaning: Standardizes country names and removes duplicates.
Exploratory Data Analysis: Understands each datasets and looks for some actionable insights.

### 2️. Popular Books Ranking (Weighted Rating)
Computes a weighted rating based on the number of ratings and average rating.

### 3. Cold-Start Recommendation for New Users
Hybrid Strategy:
- 60% Popular Books (global best-sellers)
- 40% Location-Based (top books in the user’s country)

### 4. Collaborative Filtering for current users
Item-Item Collaborative Filtering (Item-CF): Uses cosine similarity to recommend books based on past interactions.
Performance Comparison:
- Item-CF training time is 3.8x faster than User-CF

--- 

## 📌 Future Enhancements (As The Report)
Integrates Sapling Similarity Collaborative Filtering (SSCF), LSTM sentiment modeling, and demographic-based recommendation enhancements as potential improvements to the system.

✅ Real-Time Personalization: Dynamically update recommendations based on user behavior and recent interactions.

✅ Hybrid Sentiment-Aware Recommender: Integrate LSTM-RNN for sentiment analysis on user reviews, capturing emotional tone to enhance book recommendations.

✅ Advanced Collaborative Filtering: Implement Sapling Similarity Collaborative Filtering (SSCF) to improve static user preference modeling through interaction-based similarity scoring.

✅ Demographic-Based Personalization: Incorporate user age, location, and language preferences to refine recommendations, adjusting similarity scores using a weighted hybrid model:

$$
\text{Hybrid Similarity} = \alpha \cdot \text{SSCF Similarity} + (1 - \alpha) \cdot \text{Demographic Similarity}
$$

where:
- $\alpha$ is the weighting factor.
- **SSCF Similarity** captures interaction-based user similarity.
- **Demographic Similarity** accounts for similarities based on user attributes (e.g., age, location, language).

✅ Deep Learning-Based Sentiment Analysis: Leverage LSTM and CNN models to extract sentiment-based features from user reviews, improving recommendation accuracy.

✅ Graph-Based Hybrid Model: Explore Graph Neural Networks (GNNs) for enhanced collaborative filtering by capturing deeper item-user interactions.
