# Content-Based Song Recommender

A content-based **song recommendation system** built with Python using **TF-IDF and cosine similarity**.

The project combines exploratory data analysis of Spotify-style audio features with a text-based recommendation engine that recommends songs based on titles, artists, and genres.

## Project Overview

Music recommendation systems help users discover songs that match their interests.

This project implements a simple **content-based recommendation system** that compares the textual characteristics of songs and returns the most similar tracks based on a user's text input.

## Objectives

This project aims to:

* Perform exploratory data analysis on a music dataset.
* Identify and handle data quality issues.
* Analyze distributions and relationships between audio features.
* Explore genre representation and music trends over time.
* Build a content-based recommendation system.
* Generate five song recommendations from a text input.
* Evaluate the relevance of recommendations using different types of queries.

## Data Cleaning

The dataset was inspected for:

* Duplicate records
* Missing values
* Inconsistent release-date formats
* Missing artist genres

The following preprocessing steps were performed:

* Removed duplicate rows.
* Removed records missing critical song identifiers.
* Imputed missing `Acousticness` and `Tempo` values using the median.
* Replaced missing artist genres with `Unknown`.
* Extracted release years from album release dates.

The cleaned dataset was saved as:

```text
cleaned_song_recommendation.csv
```

## Exploratory Data Analysis

The project explores several Spotify-style audio features, including:

* Popularity
* Danceability
* Energy
* Loudness
* Speechiness
* Acousticness
* Instrumentalness
* Liveness
* Valence
* Tempo

### Visualizations

The analysis includes:

* Numerical feature distributions
* Correlation heatmap
* Outlier detection using boxplots
* Top 10 genre analysis
* Audio feature trends over time

The analysis also examines how audio characteristics such as **Energy, Loudness, Danceability, Valence, and Acousticness** relate to one another.

## Recommendation System

A content-based recommendation approach was implemented using:

### TF-IDF

Text information from the following fields was combined:

```text
Track Name
Artist Name(s)
Artist Genres
```

These text features were transformed into numerical representations using **TF-IDF (Term Frequency–Inverse Document Frequency)**.

### Cosine Similarity

Cosine similarity was then used to measure the similarity between the user's input and songs in the dataset.

The recommendation function returns the **five most similar songs**.

```python
recommend_songs(input_text, n=5)
```

## Recommendation Examples

The system was tested using three different input types:

### 1. Song Title

```text
If I Ain't Got You
```

The system was able to identify the original song and recommend other songs with similar textual characteristics.

### 2. Genre Keyword

```text
Rock and Roll
```

The recommendations included songs associated with rock-related terms and genres.

### 3. Artist Name

```text
Lionel Richie
```

The system returned songs associated with the specified artist.

## Key Insights

The exploratory analysis showed several patterns in the dataset:

* Audio features have different distributions and levels of variability.
* Energy and Loudness show a relatively strong positive relationship.
* Danceability is positively associated with Energy and Valence.
* Acousticness tends to show a negative relationship with Energy and Loudness.
* The dataset contains a concentration of popular music genres.
* Some audio features show changes in their average values across release years.

The recommendation experiment demonstrates that text-based similarity can be used as a simple approach for generating music recommendations.

## Limitations

This recommendation system is **content-based** and relies primarily on textual information.

It does not currently incorporate:

* User listening history
* User ratings
* Collaborative filtering
* Personalized user profiles
* Real-time streaming data

Therefore, recommendations are based on similarity between the input text and song metadata rather than individual user preferences.
