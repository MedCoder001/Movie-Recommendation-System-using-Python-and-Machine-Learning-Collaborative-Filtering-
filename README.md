# Movie Recommendation System using Python and Machine Learning (Collaborative Filtering)

This project implements a movie recommendation system using collaborative filtering, a machine learning technique. Collaborative filtering is based on the idea that users who have agreed in the past tend to agree again in the future. In this system, we leverage user ratings to recommend movies to users based on their preferences and similarities with other users.

## Overview of MovieLens dataset Used

The MovieLens dataset provides insights into user ratings and tagging activities from MovieLens, a movie recommendation service. It includes 100,836 ratings and 3,683 tag applications across 9,742 movies, generated by 610 users between March 29, 1996, and September 24, 2018. This dataset was last updated on September 26, 2018.

Users were randomly selected for inclusion, having rated at least 20 movies. No demographic information is provided, with each user represented solely by an ID.

The dataset comprises four files: `links.csv`, `movies.csv`, `ratings.csv`, and `tags.csv`, each offering specific insights into movie ratings, tags, and metadata.

## Usage License

The University of Minnesota and the GroupLens Research Group do not guarantee the correctness or suitability of the data for any purpose. However, researchers may use the dataset for research purposes under certain conditions, including acknowledgment in publications and adherence to specified license conditions. Commercial use requires permission from a GroupLens faculty member.

## Citation

To acknowledge the use of this dataset in publications, users are encouraged to cite the following paper:

> F. Maxwell Harper and Joseph A. Konstan. 2015. The MovieLens Datasets: History and Context. ACM Transactions on Interactive Intelligent Systems (TiiS) 5, 4: 19:1–19:19. [DOI](https://doi.org/10.1145/2827872)

## Further Information About GroupLens

GroupLens, based at the University of Minnesota, conducts research in various fields, including recommender systems, online communities, and digital libraries. The MovieLens dataset is sourced from their movie recommender system, MovieLens. Users can explore MovieLens and collaborate with GroupLens by visiting [movielens.org](http://movielens.org) or contacting [grouplens-info@cs.umn.edu](mailto:grouplens-info@cs.umn.edu).

## Content and Use of Files

### Formatting and Encoding

The dataset files are encoded in UTF-8 and written in comma-separated values (CSV) format with a single header row. Columns containing commas are escaped using double quotes.

### User IDs

User IDs are anonymized and consistent across `ratings.csv` and `tags.csv`.

### Movie IDs

Only movies with at least one rating or tag are included, and movie IDs are consistent across the dataset files.

### Ratings Data File Structure (`ratings.csv`)

Each line represents one rating of one movie by one user, with the format: `userId,movieId,rating,timestamp`.

Ratings are on a 5-star scale, with timestamps in seconds since January 1, 1970 (UTC).

### Tags Data File Structure (`tags.csv`)

Each line represents one tag applied to one movie by one user, with the format: `userId,movieId,tag,timestamp`.

Tags are user-generated metadata, with timestamps in seconds since January 1, 1970 (UTC).

### Movies Data File Structure (`movies.csv`)

Each line represents one movie, with the format: `movieId,title,genres`.

Movie titles include release years in parentheses, and genres are pipe-separated.

### Links Data File Structure (`links.csv`)

Each line represents one movie, with the format: `movieId,imdbId,tmdbId`.

Movie IDs link to MovieLens, IMDb, and TMDb.

## Cross-Validation

Prior versions included pre-computed cross-folds or scripts for cross-fold computation, but these are not included in the current dataset. Users interested in cross-validation for recommender systems can refer to [LensKit](http://lenskit.org) for tools, documentation, and code examples.


## Project Overview

### Objective
The objective of this project is to recommend movies to users based on their past ratings and similarities with other users.

### Dataset
The dataset used in this project consists of two main files:
- `ratings.csv`: Contains user ratings for different movies.
- `movies.csv`: Contains information about the movies, including titles and genres.

## Implementation Steps

1. **Data Preparation**:
    - Read the dataset into Pandas DataFrames.
    - Merge the `ratings` and `movies` DataFrames.
    - Transform the data into a user-item matrix, where each row represents a user, each column represents a movie, and the values represent the ratings given by users to movies.

2. **Data Cleaning**:
    - Remove movies with less than 10 users who rated them.
    - Fill the remaining NaN values with 0.

3. **Similarity Matrix**:
    - Calculate the similarity between movies based on user ratings using the Pearson correlation coefficient.
    - Build a similarity matrix where each cell represents the similarity score between two movies.

4. **Recommendation Function**:
    - Define a function to generate movie recommendations for a given user based on their ratings.
    - For each movie rated by the user, calculate the similarity scores with other movies and adjust them based on the user's rating.
    - Sort the movies based on their adjusted similarity scores and recommend the top-rated ones.

5. **Testing**:
    - Test the recommendation function with sample user ratings.
    - Generate recommendations for a set of movies rated by the sample user.

## How to Use
1. Ensure you have the required libraries installed (`pandas` and `numpy`).
2. Download the dataset files (`ratings.csv` and `movies.csv`) or provide your own dataset.
3. Run the provided Python script to execute the recommendation system.
4. Modify the sample user ratings to test different scenarios and generate personalized movie recommendations.

## Conclusion
This movie recommendation system offers a simple yet effective way to provide personalized movie recommendations to users based on their past ratings and similarities with other users. Collaborative filtering techniques like this can be used in various applications, including movie streaming platforms, e-commerce websites, and social media platforms, to enhance user experience and engagement.


**Happy movie watching!**
