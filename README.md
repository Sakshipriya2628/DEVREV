Problem Statement:

The objective of this project is to develop an effective movie recommendation system based on users' viewing history. The project involves using a movie dataset from Kaggle or another source to build a data warehouse for data analysis. Once the data is collected and analyzed, it will be used to build a recommendation system that suggests movies to users based on various criteria, including popularity, content similarity, and user ratings.

Datasets Used:

credits.csv**: Contains information about the cast and crew of each movie.
movies_metadata.csv**: Contains metadata for each movie, such as title, genres, and popularity.
ratings.csv**: Contains user ratings for different movies.

Key Features

Popularity-Based Recommendation

- The system filters out necessary columns (`id`, `title`, `vote_count`, `vote_average`, `popularity`) to find popular movies.
- A custom rating formula is used to calculate a score for each movie based on vote count, vote average, and popularity.
- The most popular movies are then recommended based on this score.

Content-Based Recommendation

- Content-based filtering is used to recommend similar movies based on the content of the movie itself, including genres, cast, keywords, and director.
- The `ast` module is used to convert string representations of lists and dictionaries into actual Python objects for easier manipulation.
- Various functions are used to extract, clean, and transform features like genres, cast, crew, production companies, and keywords into useful tags.
- The `CountVectorizer` is used to convert these tags into numerical data, which is then used to calculate cosine similarity between movies.
- The system recommends movies that are most similar to a given movie based on these calculated similarities.

User-Based Collaborative Filtering

- User-based collaborative filtering recommends movies based on the preferences of users with similar tastes.
- The dataset is filtered to include only users who have rated at least 100 movies and movies that have been rated at least 50 times.
- A pivot table is created with movies as rows and users as columns, with the ratings as values.
- The `NearestNeighbors` algorithm is used to find the nearest neighbors (similar movies) based on user ratings.
- The system then suggests movies based on these nearest neighbors.

Code Structure

Data Loading and Preprocessing:
  The initial part of the code loads the datasets and merges them to form a comprehensive dataset that includes information about movies, cast, crew, and user ratings.

Popularity-Based Recommendation:
  The code calculates a custom score for each movie and recommends the most popular ones.

Content-Based Recommendation:
  The code extracts, cleans, and transforms features from the dataset and then calculates similarities between movies using cosine similarity. Based on these similarities, the system recommends movies similar to a given movie.

User-Based Collaborative Filtering:
  The code filters out users and movies based on predefined criteria, creates a pivot table, and then uses the `NearestNeighbors` algorithm to recommend movies based on user preferences.

How to Run?

1. Ensure you have the necessary datasets: `credits.csv`, `movies_metadata.csv`, and `ratings.csv`.
2. Install the required Python packages:
   ```bash
   pip install pandas numpy scikit-learn
   ```
3. Run the code in a Python environment (e.g., Jupyter Notebook, Python script).
4. Use the `recommend()` function for content-based recommendations and `suggetions()` function for user-based recommendations by passing the movie title as a parameter.

Example Usage

- To get content-based recommendations:
  ```python
  recommend('Titanic')
  ```
- To get user-based recommendations:
  ```python
  suggetions('Titanic')
  ```
Acknowledgements

- The datasets used in this project were sourced from [Kaggle](https://www.kaggle.com/).
- Thanks to the developers of the Python libraries used in this project, including Pandas, NumPy, and Scikit-learn.
