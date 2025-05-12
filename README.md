# MovieLens-Data-Cleaning-and-Ratings-Analysis2
This code is a data preprocessing and exploration pipeline designed for analyzing movie ratings data. It includes steps like data loading, merging, cleaning, transformation, and basic visualization. Below is a theoretical explanation of what each section does conceptually:

🎬 Objective:
To process and clean movie data by:

Merging movie metadata with user ratings
Extracting release years from movie titles
Cleaning and standardizing the data
Exploring rating distributions
🔹 1. Importing Required Libraries
numpy and pandas: For numerical and tabular data manipulation.
datetime: For date/time operations (though not used in this code).
seaborn and matplotlib.pyplot: For data visualization.
ipywidgets: Enables interactive widgets (also not used directly here).
🔹 2. Loading Datasets
movies.csv contains information like movie ID, title, and genre.
ratings.csv contains movie ratings by users.
Purpose: To gather two separate datasets for integration and analysis.

🔹 3. Merging Datasets
Merges the movies and ratings datasets on the shared key movieId.

Ensures each rating is associated with its movie title and genre.

Concept: This is called a relational join — integrating multiple data sources using a shared identifier.

🔹 4. Dropping Irrelevant Columns
Columns like userId, timestamp, and movieId are not needed for analysis of movie-level data.

These are removed to reduce noise and simplify the dataset.

🔹 5. Aggregation with Pivot Table
Groups the data by title and genres, then computes the average rating for each unique movie.

Theory: This is data aggregation, where raw data is summarized to show higher-level insights.

🔹 6. Data Visualization
A histogram of the ratings shows how ratings are distributed across movies.

Goal: To understand the general trends and patterns in user ratings.

🔹 7. Extracting the Year from Movie Titles
Many movie titles contain the release year in parentheses (e.g., "Titanic (1997)").

The code splits the title and assumes the last part is the year.

Concept: This is feature extraction, turning embedded information (year in title) into a separate, usable column.

🔹 8. Cleaning the Year Data
Removes unwanted characters like brackets.
Replaces dirty or incorrect values manually.
Converts the year column to numeric format and drops rows with invalid years.
Goal: To ensure the year of release is clean, complete, and usable for time-based analysis.

🔹 9. Cleaning Movie Titles
After extracting the year, the code removes it from the movie title.

This results in a clean movie title (e.g., "Titanic" instead of "Titanic (1997)").

Concept: This is part of data normalization — separating concerns (title vs. year) and making data more structured.

✅ Final Output:
A cleaned and aggregated dataset with:

Movie title (without year)
Genre
Average rating
Year of release (as integer)
This prepares the data for further analysis, like trends over time, genre-based ratings, or recommendation systems.
