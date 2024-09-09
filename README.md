# Music-Recommender-System-SVD

### Description
This project implements a music recommender system using Singular Value Decomposition (SVD) to predict user listening preferences. It leverages collaborative filtering techniques to identify latent patterns in user-song interaction data, providing personalized song recommendations based on user listening history. 

### Part 1: Data Cleaning and Exploratory Data Analysis (EDA) for SVD Recommender System
This section focuses on preparing the data and exploring key patterns to build an effective SVD-based music recommender system. The notebook is structured into two main parts: Data Cleaning and Exploratory Data Analysis (EDA).

#### Data Cleaning
- Cleaning the Songs Dataset:
- Remove duplicates.
- Handle null values by imputing where possible.
- Make decisions on null values that cannot be imputed.

#### Cleaning the User-Song Interaction Dataset (Triplets Data):
- Check for duplicates.
- Check for null values.
- Exploratory Data Analysis (EDA)

#### Analysis of Songs:
1. Identify the top 10 songs with the most listens, along with visualizations.
2. Find songs with the highest average number of listens (top 10).
3. Determine songs with the highest number of unique listeners (top 10).
4. Visualize the most popular artists by total listens (top 10).
5. Identify artists with the highest average number of plays (top 10).
6. Analyze the most polarizing songs based on the largest standard deviation in listen count.
7. Conduct analysis by year.

#### Item-Item Relationships using Cosine Similarity:

Create a Compressed Sparse Row (CSR) matrix of song data.
Compute cosine similarity between songs.
Form a data frame of similarity scores.
Filter for the top 10 most similar songs by song IDs.
Convert song IDs to their corresponding titles and artists.
Filter for a threshold level of similarity.
Visualize similarities using a heatmap.

#### User-Item Relationships using Cosine Similarity:

Review listen count statistics.
Filter for listen counts below the median.
Filter and sample the matrix to manage user quantity.
Compute cosine similarity for a sample of users.
Analyze the similarity between 10 sampled users and all other users.
Display results in a heatmap. 

### Part 2: Constructing the SVD Music Recommender System

In this section, we build and evaluate a music recommender system using Singular Value Decomposition (SVD). The focus is on leveraging collaborative filtering techniques to predict user preferences and provide personalized song recommendations.

Steps to Build the SVD Recommender System

#### Data Preparation:

Normalize the user-song interaction matrix.
Convert the matrix into a sparse format for efficient computation.
Apply data splitting techniques to create training, validation, and holdout sets.

#### Implementing SVD:

Perform matrix factorization using SVD to decompose the user-song matrix into latent factors.
Define the number of latent factors (k) to optimize model performance.
Handle computational constraints by limiting k and experimenting with different values.

#### Model Training and Evaluation:

Train the SVD model on the training dataset.
Evaluate the model on the validation set to assess performance and tune hyperparameters.
Test the model on the holdout set to measure generalization and avoid overfitting.
Compute Root Mean Square Error (RMSE) for different k values to analyze the model's accuracy.

#### Cross-Validation Analysis:

Perform k-fold cross-validation to rigorously evaluate model performance.
Compare RMSE across different folds to assess consistency and identify potential overfitting.
Analyze the variation in RMSE to determine if specific data subsets impact performance.

#### Hyperparameter Tuning:

Experiment with different values of k to find the optimal number of latent factors.
Explore alternative regularization techniques to minimize overfitting.
Adjust learning rates and other parameters to improve model convergence.

#### Recommendations Generation:

Use the trained SVD model to generate song recommendations for users.
Rank songs based on predicted listen counts or scores.
Filter recommendations above a certain threshold to ensure relevance.

#### Results Interpretation and Visualization:

Visualize the distribution of predicted listen counts versus actual listen counts.
Analyze the impact of different k values on model performance.
Create visualizations to illustrate the effectiveness of recommendations.

#### Future Improvements:

Discuss potential improvements, such as handling larger k values, adding more features, or refining the recommendation algorithm.
Explore techniques to address computational constraints and enhance scalability.
