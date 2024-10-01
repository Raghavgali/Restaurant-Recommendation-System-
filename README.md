# Restaurant-Recommendation-System

Project Overview

This project aims to build a Restaurant Recommendation System leveraging customer data from Yelp, including user reviews, ratings, and business information. The system provides personalized restaurant recommendations based on user preferences, dining history, and personality traits using collaborative filtering, content-based filtering, and a personality-driven approach with BERT for user personality prediction.

Table of Contents

	1.	Problem Statement
	2.	Dataset
	3.	Methodology
	•	Exploratory Data Analysis (EDA)
	•	Collaborative Filtering
	•	Content-Based Filtering
	•	Personality-Based Recommendation
	4.	Results
	5.	Technologies Used
	6.	Contributors

Problem Statement

With the rising demand for personalized dining experiences, the goal of this project is to analyze customer data and develop a robust recommendation system. The system recommends new restaurants that align with the user’s tastes, enhancing their dining experiences by utilizing past reviews, ratings, and other features.

Dataset

The Yelp dataset consists of multiple files containing detailed information about businesses, user reviews, and user profiles:

	•	Business.json: Includes business details like ID, name, location, rating, and categories.
	•	Review.json: Contains individual reviews, star ratings, review text, and user-business associations.
	•	User.json: Contains user profiles with details such as review count and average rating.

Methodology

Exploratory Data Analysis (EDA)

EDA was conducted to identify trends in user reviews, ratings, and restaurant popularity. Key observations include the frequency of restaurant reviews and the distribution of ratings over time.

Collaborative Filtering

Collaborative filtering was applied using Matrix Factorization techniques, such as SVD and ALS. The system uses implicit feedback (ratings) to suggest restaurants based on similarities between users and restaurants. Due to the sparsity (99.4%) of the dataset, matrix factorization models effectively handled recommendations.

	•	SVD with 100 features.
	•	ALS with 50 features (higher NDCG, better handling of sparse matrices).

Content-Based Filtering

Content-based filtering suggests restaurants similar to those a user has liked based on the restaurant’s attributes (e.g., cuisine, rating, review count). The process includes:

	•	One-Hot Encoding of categorical features.
	•	Normalization of ratings and review counts using MinMaxScaler.
	•	PCA to reduce dimensionality and find optimal components.
	•	K-Means Clustering to group similar restaurants.

Personality-Based Recommendation

This component uses BERT fine-tuned on MBTI personality types to predict user personalities based on their reviews. Each user is classified into one of five personas:

	•	The Adventurous Foodie
	•	The Comfort Food Connoisseur
	•	The Health-Conscious Eater
	•	The Culinary Explorer
	•	The Social Foodie

Using these personas, restaurants are recommended based on the dining experiences that match the user’s personality.

Results

The ALS model outperformed other models, achieving higher NDCG scores while utilizing fewer features. Personality-based recommendations provided more refined suggestions tailored to user preferences, enhancing the dining experience.
