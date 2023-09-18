# Phase4project
Movie Recommendation System README
## Overview('\n')
Welcome to MovieXplosion's Movie Recommendation System! MovieXplosion is a streaming platform dedicated to enhancing user satisfaction by providing personalized movie recommendations to keep users engaged and satisfied. This project employs collaborative filtering, content-based filtering, and hybrid approaches to suggest movies to users, ultimately improving their experience on the platform.

## Problem Statement (\n)
The existing recommendation system on MovieXplosion has several limitations, including subpar recommendations, low user engagement, and retention issues. New users receive generic recommendations, and existing users lack tailor-made suggestions. The goal of this project is to address these issues and deliver relevant movie recommendations to all users.

## Data (\n)
I sourced data from MovieLens, utilizing the small dataset due to computational constraints. This dataset includes information about movies, user ratings, and other relevant details.
The data files look as follows:(\n)
Movies File(\n)
It contains information about the movies.(\n)
movieId - Unique identifier for each movie.(\n)
title - The movie titles.(\n)
genre - The various genres a movie falls into.(\n)
Ratings file(\n)
It contains the ratings for the movies by different users.(\n)
userId - Unique identifier for each user(\n)
movieId - Unique identifier for each movie.(\n)
rating - A value between 0 to 5 that a user rates a movie on. A higher rating indicates a higher preference.(\n)
timestamp - This are the seconds that have passed since Midnight January 1, 1970(UTC)(\n)
Tags file(\n)
It has user-generated words or short phrases about a movie with the meaning or value being determined ny the specific user.(\n)
userId - Unique identifier for each user(\n)
movieId - Unique identifier for each movie.(\n)
tag - A word or phrase determined by the user.(\n)
timestamp - This are the seconds that have passed since Midnight January 1, 1970(UTC)(\n)
Links file (\n)
This are identifiers that can be used to link to other sources of movie data as provide by MovieLens.(\n)
movieId - It's an identifier for movies used by https://movielens.org. E.g., the movie Toy Story has the link https://movielens.org/movies/1. (\n)
imdbId - It's an identifier for movies used by http://www.imdb.com. E.g., the movie Toy Story has the link http://www.imdb.com/title/tt0114709/. (\n)
tmdbId - is an identifier for movies used by https://www.themoviedb.org. E.g., the movie Toy Story has the link https://www.themoviedb.org/movie/862. (\n)

Data Preparation(\n)
To prepare the data, I addressed a minor issue with only 8 rows containing missing values in one column. I merged dataframes from ratings.csv, movies.csv, and tags.csv to create a comprehensive dataset. (\n)

Modeling Process
I leveraged the Surprise library to load and analyze the data. Three distinct models were employed: SVD (Singular Value Decomposition), KNN Basic, and KNN with Means. I did evaluated model performance using RMSE (Root Mean Squared Error) as our metric and fine-tuned the models using GridSearchCV to identify the best parameters.

Evaluation
In the initial modeling phase, models produced the following RMSE scores:

SVD: RMSE = 0.3903
KNN Basic: RMSE = 0.55

SVD emerged as the top-performing model with an initial RMSE of 0.39. After parameter tuning, SVD further improved, achieving an RMSE of 0.29

Conclusion
In conclusion, the Movie Recommendation System's most effective model is SVD, consistently outperforming the other models. It successfully addresses the cold start problem by providing recommendations to both new and existing users. With SVD as the core recommendation engine, MovieXplosion is better equipped to keep users engaged and satisfied by offering personalized movie suggestions based on their preferences.
