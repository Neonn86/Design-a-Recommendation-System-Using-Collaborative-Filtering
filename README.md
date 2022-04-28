# Recommendation System Using Collaborative Filtering
## Objective
 The goal is to build a recommendation system exploring 3 **collaborative filtering** techniques: 
 - User-based Filtering
 - Item-based Filtering
 - Matrix Factorization

## Data
- The movie rating data consists of ratings from 280 users for 50 movies. The users are from 2 sources - 96 UC Davis MSBA students and 184 unnamed users. 
- The rating score stretches from 1 to 5 indicating the least complimentary to the most, and includes NULL representing never watched by the user. 
- 3 users (A1, A2 and A3) were included to make cold start rating predictions.

## Structure
### Building Models and Recommend to existing users
- For User-based and Item-based filtering, we use the **Cosine Similarity** as the theorem to calculate the similarity.
- For Matrix Factorization, we use the **Singular Value Decomposition (SVD) algorithm**. To avoid overfitting, we use **k-fold cross-validation** to find the optimal number of epochs for training and size of the latent vectors.
- Among the 3 collaborative filtering techniques experimented with, the user-based one has the lowest MSE error, but the Matrix Factorization model allows us to explain and make predictions without any user or item bias, we choose to use it for our recommendation system.
### Recommend to new users
To tackle the cold start problem, we remove the respective user biases in the available ratings by standarize the data and then calculate the average rating. To get new users' ratings, we assume their biases as 0 and add the average bias
 
## Conclusion
-  Collaborative filtering effectively predicts ratings for a given user-item pair.
-  In case of new users, existing movie rating data could be used to recommend content for them by discounting the individual user bias from the movie ratings.
-  Recommending a combination of highly rated movies and the most popular movies to new users could be a good starting point.
