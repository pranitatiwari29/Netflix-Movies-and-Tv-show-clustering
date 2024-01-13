# Netflix Movies and TV Shows Clustering

## Overview

This project aims to optimize Netflix's content recommendation system for TV Shows and Movies by leveraging advanced data analysis and clustering techniques. The primary objectives include conducting detailed Exploratory Data Analysis (EDA), implementing text-based clustering to categorize similar content, and developing a sophisticated recommendation system to enhance user experience.

**Table of Contents**

1. [Overview](#overview)
2. [Problem Statement](#problem-statement)
3. [Data Wrangling](#data-wrangling)
4. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
5. [Feature Engineering ](#feature-engineering)
6. [ML Model Implementation](#ml-model-implementation)
7. [Recommendation System](#recommendation-system)
8. [Conclusion](#conclusion)

## Problem Statement
The goal of this project is to analyze the Netflix catalog of movies and TV shows, which was sourced from the third-party search engine Flixable, and group them into relevant clusters. This will aid in enhancing the user experience and prevent subscriber churn for the world's largest online streaming service provider, Netflix, which currently boasts over 220 million subscribers as of 2022-Q2. The dataset, which includes movies and TV shows as of 2019, will be analyzed to uncover new insights and trends in the rapidly growing world of streaming entertainment.

## Data Wrangling
This section focuses on the initial phase of the project. We've organized the data wrangling process into four distinct sections:

#### **1. Handling Null Values:**
* Imputed 'Unknown' for 'director' and 'cast'.
* Imputed with the mode for the 'country'.
* Dropped null values in 'date_added' and 'rating' (those with a lower percentage).
#### **2. Unnesting Values:**
We performed unnesting on the following features:
* 'director'
* 'cast'
* 'listed_in'
* 'country'
#### **3. Typecasting:**
We adjusted the data types of the following features:
- 'duration' was converted to an integer (excluding 'min' and 'seasons' from the values).
- 'date_added' was converted to datetime in the required format.
- Feature Extraction:
Additional features were extracted from 'date_added':
'date'
'month'
'year'
#### **4. Rating Categorization:**
Given the varied coded categories in the 'rating' column, we created five bins to distribute values:
- Adult: TV-MA, NC-17
- Restricted: R, UR
- Teen: PG-13, TV-14
- All Ages: TV-G, TV-Y, TV-Y7, TV-Y7-FV, PG, G, TV-PG
- Not Rated: NR

## Exploratory Data Analysis (EDA)
Detailed exploration of the dataset to uncover patterns, insights, and trends related to Netflix Movies and TV Shows. Following are the findings from EDA which are crucial for subsequent phases of the project:

  - **Content Distribution:** The dataset is skewed towards movies, constituting 69.14%, while TV shows make up 30.86%.
  - **Target Audience:** Adult and teen audiences are the primary focus of the majority of shows, as indicated by the content's nature and rating.
  - **Geographical Origin:** The United States is the predominant source of movies and TV shows, followed by India and the United Kingdom.
  - **Popular Genres:** International Movies, drama, and comedies emerge as the most popular genres on the Netflix platform.
  - **Content Recency:** Netflix emphasizes recently released content, with a larger quantity of newer movies and TV shows compared to older ones.
  - **Shift in Focus:** A noticeable decrease in the number of movies added in 2020 suggests a potential shift in focus towards introducing more TV series.
  - **Seasonal Pattern:** December exhibits the highest number of content additions, indicating a focus on the winter season.
  - **TV Show Seasons:** A significant proportion of TV shows have only one season, suggesting a preference for shorter series.
  - **Movie Durations:** The majority of movies fall within the 60 to 120-minute range, reflecting a preference for standard-length films.


## Feature Engineering
**1. Attributes for clustering:**

Cast, country, genre, director, rating, and description.

**2. Textual Data Preprocessing:**
  - Expand Contraction
  - Remove stopwords and lower case
  - Removing Punctuations
  - Lemmatization
  - Tokenization
  - Text Vectorization

**3. Dimesionality Reduction:**

Dimensionality reduction was achieved through Principal Component Analysis (PCA), wherein the number of components was restricted to 4000, effectively capturing over 80% of the variance in the data.

## ML Model Implementation
The implementation of machine learning models, specifically K-Means and Hierarchical Clustering, to categorize and cluster similar content. The optimal number of clusters and effective algorithms are determined through rigorous analysis.

**3.1. K Means Clustering:**
- The optimal number of clusters were built after visualizing the elbow curve and the Silhouette score.
- Highest Silhouette score is obtained for 6 clusters using k-means clustering. Hence, the number of clusters for k-means clustering was taken as 6.
- Silhouette score at 6 clusters: 0.0082

**3.2. Hierarchical Clustering:**
- Clusters were built using the Agglomerative clustering algorithm, and the optimal number of clusters were built after visualizing the dendogram.
- From the dendogram, at an Euclidean distance of 3.8 units, 12 clusters can be built. Hence the number of clusters were taken as 12.
- Algorithm: Agglomerative clustering
- Distance: Euclidean
- Linkage: Ward

## Recommendation System
Utilizing the insights gained from clustering, a content-based recommender system is developed. The system leverages cosine similarity and the generated similarity matrix to provide personalized content recommendations.

## Conclusion
Summarizes the key findings, contributions, and potential business impacts of the project, highlighting the advancements in content categorization and recommendation for Netflix Movies and TV Shows.

Feel free to explore, contribute, and provide feedback for continuous improvement!

