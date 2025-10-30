# Unsupervised News Topic Modeling

This project applies Phase 1 NLP techniques to an **unsupervised** learning problem. Instead of classifying text into predefined labels (like spam/ham), we will discover hidden thematic structures (topics) from a collection of unlabeled news articles.

## 🎯 Goal

To use `TF-IDF` and `Non-negative Matrix Factorization (NMF)` to automatically extract and interpret the main topics from a text corpus.

## 🛠️ Techniques & Libraries Used

* **Text Representation:** `TF-IDF` (Term Frequency-Inverse Document Frequency). This is crucial for giving "topic-specific" words a higher weight.
* **Topic Modeling Algorithm:** `NMF (Non-negative Matrix Factorization)`. This is a dimensionality reduction technique that is excellent for this task, as it creates easily interpretable, additive topics.
* **Core Libraries:**
    * `scikit-learn`: For the dataset, `TfidfVectorizer`, and `NMF` model.
    * `Pandas` & `Matplotlib` (for viewing results).

## 📊 Dataset

We will use the famous **"20 Newsgroups"** dataset. It's a classic dataset for topic modeling and is conveniently built into the `scikit-learn` library. It contains ~18,000 newsgroup posts, partitioned (by the dataset creators, not by us) across 20 different topics.

**Our Challenge:** We will *ignore* the labels it comes with and see if our unsupervised NMF model can "find" these 20 topics on its own.

## 📈 Process

1.  **Load Data:** Fetch the "20 Newsgroups" dataset using `scikit-learn`.
2.  **Vectorize (Feature Extraction):**
    * Initialize `TfidfVectorizer`.
    * Critically, we will filter out words that are too common (`max_df`) or too rare (`min_df`) to get more meaningful topics.
    * We will also remove `stop_words`.
    * Fit and transform the text data into a TF-IDF matrix.
3.  **Train NMF Model:**
    * Initialize `NMF` and specify the number of topics to find (e.g., `n_components=20`).
    * Fit the NMF model to the TF-IDF matrix.
4.  **Interpret Topics:**
    * This is the most important step. We will inspect the *components* of the fitted model.
    * For each topic, we will find the top 10-15 words that have the highest weight.
    * By looking at these words (e.g., "game, team, players, season"), we can manually label the topic (e.g., "Sports").
5.  **Test Model:**
    * We will take a new, unseen document and ask the model to predict which topic it belongs to.


### Created by vira...
