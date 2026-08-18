# Electronics Recommendation System

A machine learning-based **Electronics Recommendation System** developed using **Python** and collaborative filtering techniques. The project analyzes user-product rating interactions and generates personalized product recommendations based on user preferences, product popularity, and similarity between users and products.

The system uses an electronics ratings dataset containing **7.8 million+ ratings**, with information about users, products, ratings, and timestamps.

## Features

### Exploratory Data Analysis

* Analyze the complete ratings dataset
* Check dataset shape and data types
* Check missing values and duplicate records
* Analyze rating distribution
* Identify the most active users
* Identify the most rated products
* Calculate average product ratings
* Analyze ratings over time

### Data Preprocessing

The dataset is filtered to improve recommendation quality by selecting:

* Users with at least **50 ratings**
* Products with at least **50 ratings**

A **User-Item Matrix** is then created to represent the interaction between users and products.

### Popularity-Based Recommendation

The popularity-based system recommends products using:

* Average product rating
* Number of ratings received

Products are ranked based on their average rating and rating count to identify highly rated and frequently reviewed electronics products.

### User-Based Collaborative Filtering

User-based collaborative filtering identifies users with similar rating patterns using **Cosine Similarity**.

The system:

1. Selects a target user
2. Calculates similarity with other users
3. Finds the top 5 similar users
4. Collects products rated by similar users
5. Removes products already rated by the target user
6. Recommends the highest-rated products

### Item-Based Collaborative Filtering

Item-based collaborative filtering calculates similarity between products using the user-item matrix.

It identifies products that have similar rating patterns and recommends the most similar products to a selected product.

### SVD Recommendation

**Singular Value Decomposition (SVD)** is implemented using the Surprise library.

The model:

* Splits the ratings into training and testing data
* Trains an SVD model
* Predicts user ratings for products
* Ranks products according to predicted ratings
* Generates personalized recommendations

### Hybrid Recommendation System

The project combines recommendations generated from:

* User-Based Collaborative Filtering
* Item-Based Collaborative Filtering
* SVD

The products from these approaches are combined to create a broader recommendation list.

## Data Structure

The original dataset contains four columns:

```text
User_id
Product_id
Rating
Timestamp
```

The timestamp is converted from Unix time into a readable datetime format, and the year is extracted for analyzing rating trends.

## System Flow

```text
                 Electronics Ratings Dataset
                           |
                           v
                  Data Cleaning & EDA
                           |
                           v
                 User/Product Filtering
                           |
                           v
                  User-Item Matrix
                           |
          +----------------+----------------+
          |                |                |
          v                v                v
      Popularity       User-Based        Item-Based
   Recommendation          CF                CF
          |                |                |
          +----------------+----------------+
                           |
                           v
                     SVD Model
                           |
                           v
                 Hybrid Recommendations
```

## Technology Stack

* **Language:** Python
* **Data Processing:** Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-learn
* **Recommendation System:** Scikit-Surprise
* **Algorithms:** Cosine Similarity, SVD
* **Development Environment:** Jupyter Notebook / VS Code

## Project Structure

```text
Electronics-Recommendation-System/
│
├── Electronics_rating.csv
├── user_item_matrix.csv
├── rec_systems.ipynb
├── ncf_recommendation_model.keras
└── README.md
```

### File Description

**`Electronics_rating.csv`**

Original electronics product ratings dataset containing user IDs, product IDs, ratings, and timestamps.

**`user_item_matrix.csv`**

Generated user-item matrix containing the ratings of users for different products. This matrix is used for collaborative filtering and similarity calculations.

**`rec_systems.ipynb`**

Main Jupyter Notebook containing:

* Data loading
* Data preprocessing
* Exploratory Data Analysis
* Rating analysis
* User and product filtering
* User-item matrix creation
* Popularity-based recommendation
* User-based collaborative filtering
* Item-based collaborative filtering
* SVD recommendation
* Hybrid recommendation system

**`ncf_recommendation_model.keras`**

Saved Keras model file included with the project.

## How to Run

### Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scikit-surprise
```

### Run the Notebook

Open:

```text
rec_systems.ipynb
```

in **Jupyter Notebook or VS Code**.

Place `Electronics_rating.csv` in the same project directory and run the notebook cells sequentially.

## Key Learning Outcomes

* Worked with a large-scale ratings dataset containing 7.8M+ records.
* Performed exploratory data analysis on user-product interactions.
* Created a user-item interaction matrix.
* Implemented popularity-based recommendations.
* Applied cosine similarity for user-based collaborative filtering.
* Applied item-based collaborative filtering.
* Implemented SVD-based recommendation using Surprise.
* Combined multiple recommendation techniques into a hybrid approach.
* Gained practical understanding of real-world recommendation systems.

## Future Improvements

* Add recommendation evaluation metrics such as **Precision@K, Recall@K, MAP@K, and NDCG@K**.
* Improve the hybrid recommendation strategy by assigning weights to different models.
* Add product metadata for content-based recommendations.
* Deploy the recommendation system using **Streamlit or FastAPI**.
* Build an interactive web interface for users to receive personalized electronics recommendations.

## Conclusion

This project demonstrates the implementation of a complete **Electronics Recommendation System** using real-world user-product rating data. By combining popularity-based recommendations, user-based collaborative filtering, item-based collaborative filtering, SVD, and hybrid recommendations, the system provides multiple approaches for generating relevant electronics product recommendations.

The project provides practical experience in **data preprocessing, EDA, similarity-based recommendation, collaborative filtering, matrix-based recommendation, and machine learning model development**.
