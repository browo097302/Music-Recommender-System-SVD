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

Convert the matrix into a sparse format for efficient computation.
Apply data splitting techniques to create training, validation, and holdout sets.

#### Implementing SVD:

Perform matrix factorization using SVD to decompose the user-song matrix into latent factors.
Define the number of latent factors (k) to optimize model performance.
Handle computational constraints by limiting k and experimenting with different values.

#### Model Training and Evaluation:

Train the SVD model on the training dataset.
Generate recommendations based on highest listen counts.
Compute Root Mean Square Error (RMSE) for different k values to analyze the model's accuracy.

#### --- Take steps to improve model ---

#### Get RMSE values over the whole matrix with Truncated SVD

Implement truncated SVD on k value of only 1500 due to memory constraints.
Get new RMSE on truncated version of model.

#### Cross-Validation Analysis:

Perform k-fold cross-validation to rigorously evaluate model performance.
Compare RMSE across different folds to assess consistency and identify potential overfitting.

#### Measure new model on holdoutset:

Test model performance against holdout set as another way of evaulating performance of unseen data. 

#### Evaluation and Future Improvements:

The model demonstrates good generalization with minimal overfitting, showing only a slight increase in RMSE (+0.3) on unseen data (2.02 on training/validation data vs. 2.34 on holdout data). However, computational constraints prevented testing with higher k values, which could potentially reduce RMSE further.
Cross-validation results (RMSE of 3.96) indicate inconsistency in model performance across different subsets, likely due to data split challenges, smaller fold sizes, slight overfitting, or noise amplification.
To improve cross-validation RMSE, further investigation into specific fold performance, alternative regularization techniques, and overcoming computational constraints is recommended.
