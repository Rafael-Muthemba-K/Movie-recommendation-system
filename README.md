# Phase4project
Movie Recommendation System README
## Overview
Welcome to MovieXplosion's Movie Recommendation System! MovieXplosion is a streaming platform dedicated to enhancing user satisfaction by providing personalized movie recommendations to keep users engaged and satisfied. This project employs collaborative filtering, content-based filtering, and hybrid approaches to suggest movies to users, ultimately improving their experience on the platform.

## Problem Statement 
The existing recommendation system on MovieXplosion has several limitations, including subpar recommendations, low user engagement, and retention issues. New users receive generic recommendations, and existing users lack tailor-made suggestions. The goal of this project is to address these issues and deliver relevant movie recommendations to all users.

## Data 
I sourced data from MovieLens, utilizing the small dataset due to computational constraints. This dataset includes information about movies, user ratings, and other relevant details.
The data files look as follows: <br>
Movies File <br>
It contains information about the movies. <br>
movieId - Unique identifier for each movie. <br>
title - The movie titles. br>
genre - The various genres a movie falls into. <br>
Ratings file <br>
It contains the ratings for the movies by different users. <br>
userId - Unique identifier for each user <br>
movieId - Unique identifier for each movie. <br>
rating - A value between 0 to 5 that a user rates a movie on. A higher rating indicates a higher preference. <br>
timestamp - This are the seconds that have passed since Midnight January 1, 1970(UTC) <br>
Tags file <br>
It has user-generated words or short phrases about a movie with the meaning or value being determined ny the specific user. <br>
userId - Unique identifier for each user <br>
movieId - Unique identifier for each movie. <br>
tag - A word or phrase determined by the user. <br>
timestamp - This are the seconds that have passed since Midnight January 1, 1970(UTC) <br>
Links file  <br>
This are identifiers that can be used to link to other sources of movie data as provide by MovieLens. <br>
movieId - It's an identifier for movies used by https://movielens.org. E.g., the movie Toy Story has the link https://movielens.org/movies/1. <br>
imdbId - It's an identifier for movies used by http://www.imdb.com. E.g., the movie Toy Story has the link http://www.imdb.com/title/tt0114709/. <br>
tmdbId - is an identifier for movies used by https://www.themoviedb.org. E.g., the movie Toy Story has the link https://www.themoviedb.org/movie/862. <br>

Data Preparation <br>
To prepare the data, I addressed a minor issue with only 8 rows containing missing values in one column. I merged dataframes from ratings.csv, movies.csv, and tags.csv to create a comprehensive dataset. <br>

Modeling Process <br>
I leveraged the Surprise library to load and analyze the data. Three distinct models were employed: SVD (Singular Value Decomposition), KNN Basic. I did evaluated model performance using RMSE (Root Mean Squared Error) as our metric and fine-tuned the models using GridSearchCV to identify the best parameters. <br>

Evaluation <br>
In the initial modeling phase, models produced the following RMSE scores: <br>

SVD: RMSE = 0.3903 <br>
KNN Basic: RMSE = 0.55 <br>

SVD emerged as the top-performing model with an initial RMSE of 0.39. After parameter tuning, SVD further improved, achieving an RMSE of 0.29 <br>

Conclusion <br> 
In conclusion, the Movie Recommendation System's most effective model is SVD, consistently outperforming the other models. It successfully addresses the cold start problem by providing recommendations to both new and existing users. With SVD as the core recommendation engine, MovieXplosion is better equipped to keep users engaged and satisfied by offering personalized movie suggestions based on their preferences.
