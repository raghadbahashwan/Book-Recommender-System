# Recommendation System using Alternating Least Squares (ALS) on Spark 

A collaborative book recommendation system implemented using the Alternating Least Squares (ALS) algorithm within Apache Spark. The system provides personalized book recommendations based on user preferences.


## Configuration

- Spark configurations can be adjusted in the `spark.builder` section of the code.
- Hyperparameters like rank, regularization, and iterations are tunable in the `train_ALS` function.

## Functionalities

1. **Data Preprocessing:** The code handles the preprocessing of the Goodreads dataset, consisting of books and user ratings.

2. **Collaborative Filtering:** Utilizes ALS algorithm for collaborative filtering, allowing accurate predictions even with sparse user-item feedback.

3. **Hyperparameter Tuning:** Grid search is employed to optimize key parameters such as rank, regularization, and the number of iterations.

4. **Model Training:** The system trains on the preprocessed data, identifying the optimal configuration for effective collaborative filtering.

5. **Evaluation Metric:** The Root Mean Squared Error (RMSE) is used to evaluate the model's performance.

6. **Personalized Recommendations:** Users can receive personalized book recommendations by inputting their favorite book.

## Dataset

Dataset –Goadreads dataset 
1.	**books.csv**
Attributes: book_id, authors, title 
Shape: (10000, 3) 
  
2.	**ratings.csv**
Attributes: user_id, book_id, rating 
Shape: (5976479, 3) 

## Model
We used Alternating Least Square (ALS) Matrix Factorization

## Book Recommendation Engine Development with ALS in Apache Spark
Alternating Least Square (ALS) is one of state-of-the-art Matrix Factorization models under the context of distributed computing.

Matrix Factorization is simply a mathematical operation for matrices. It is usually more effective in collaborative filtering, because it allows us to discover the latent (hidden) features underlying the interactions between users and items (books).

There are matrix factorization methods such as Singular Value Decomposition (SVD) and Non-Negative Matrix Factorization (NMF). we chose Alternating Least Square (ALS) implemented in Spark because it is a parallel algorithm designed for a large-scale collaborative filtering problems. This method is doing a pretty good job at resolving scalability and sparseness of the user profiles, and it's simple and scales well to very large datasets.

## ALS Idea
Factorize a big matrix into two small matrix (A = Users * Items)
Use two loss functions for gradient descent
Alternative gradient descent between Users and Items matrices back and forth

## Hyperparameter Tuning
In our model, we focus on tuning three key hyperparameters for optimal performance: rank, regularization, and the number of iterations. Through an exhaustive grid search, we systematically vary these parameters. This exploration ensures the identification of hyperparameter values that minimize RMSE on a validation set, optimizing the model for accurate predictions.

maxIter: the maximum number of iterations to run (defaults to 10)
rank: the number of latent factors in the model (defaults to 10)
regParam: the regularization parameter in ALS (defaults to 1.0)

## Results
Personalized book recommendations were generated based on the input of the favorite book, "The Shadow of the Wind." The system recommended 10 books customize to the user's preferences.
The results highlight the effectiveness of the collaborative filtering approach, emphasizing accurate predictions and efficient processing of extensive datasets.

The code outputs the best model configuration, training time, and personalized book recommendations based on user input.


