# MovieLens-Data-Cleaning-and-Ratings-Analysis2
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
</head>
<body>
<p>
This code is a <strong>data preprocessing and exploration pipeline</strong> designed for analyzing movie ratings data. It includes steps like <strong>data loading, merging, cleaning, transformation, and basic visualization.</strong> Below is a theoretical explanation of what each section does conceptually: </p>

<h2>🎬 Objective:</h2>
<p>To process and clean movie data by:</p>
<ul>
    <li>Merging movie metadata with user ratings</li>
    <li>Extracting release years from movie titles</li>
    <li>Cleaning and standardizing the data</li>
    <li>Exploring rating distributions</li>
</ul>

<h3>🔹 1. Importing Required Libraries</h3>
<ul>
    <li><strong>numpy</strong> and <strong>pandas</strong>: For numerical and tabular data manipulation.</li>
    <li><strong>datetime</strong>: For date/time operations (though not used in this code).</li>
    <li><strong>seaborn</strong> and <strong>matplotlib.pyplot</strong>: For data visualization.</li>
    <li><strong>ipywidgets</strong>: Enables interactive widgets (also not used directly here).</li>
</ul>

<h3>🔹 2. Loading Datasets</h3>
<ul>
    <li><strong>movies.csv</strong> contains information like movie ID, title, and genre.</li>
    <li><strong>ratings.csv</strong> contains movie ratings by users.</li>
</ul>
<p><strong>Purpose:</strong> To gather two separate datasets for integration and analysis.</p>

<h3>🔹 3. Merging Datasets</h3>
<p>Merges the <strong>movies</strong> and <strong>ratings</strong> datasets on the shared key <code>movieId</code>.</p>
<p>Ensures each rating is associated with its movie title and genre.</p>
<p><strong>Concept:</strong> This is called a <em>relational join</em> — integrating multiple data sources using a shared identifier.</p>

<h3>🔹 4. Dropping Irrelevant Columns</h3>
<p>Columns like <code>userId</code>, <code>timestamp</code>, and <code>movieId</code> are not needed for analysis of movie-level data.</p>
<p>These are removed to reduce noise and simplify the dataset.</p>

<h3>🔹 5. Aggregation with Pivot Table</h3>
<p>Groups the data by <strong>title</strong> and <strong>genres</strong>, then computes the <strong>average rating</strong> for each unique movie.</p>
<p><strong>Theory:</strong> This is <em>data aggregation</em>, where raw data is summarized to show higher-level insights.</p>

<h3>🔹 6. Data Visualization</h3>
<p>A histogram of the ratings shows how ratings are distributed across movies.</p>
<p><strong>Goal:</strong> To understand the general <em>trends and patterns</em> in user ratings.</p>

<h3>🔹 7. Extracting the Year from Movie Titles</h3>
<p>Many movie titles contain the release year in parentheses (e.g., <em>"Titanic (1997)"</em>).</p>
<p>The code splits the title and assumes the last part is the year.</p>
<p><strong>Concept:</strong> This is <em>feature extraction</em>, turning embedded information (year in title) into a separate, usable column.</p>

<h3>🔹 8. Cleaning the Year Data</h3>
<ul>
    <li>Removes unwanted characters like brackets.</li>
    <li>Replaces dirty or incorrect values manually.</li>
    <li>Converts the <code>year</code> column to numeric format and drops rows with invalid years.</li>
</ul>
<p><strong>Goal:</strong> To ensure the year of release is clean, complete, and usable for time-based analysis.</p>

<h3>🔹 9. Cleaning Movie Titles</h3>
<p>After extracting the year, the code removes it from the movie title.</p>
<p>This results in a clean movie title (e.g., <em>"Titanic"</em> instead of <em>"Titanic (1997)"</em>).</p>
<p><strong>Concept:</strong> This is part of <em>data normalization</em> — separating concerns (title vs. year) and making data more structured.</p>

<h2>✅ Final Output:</h2>
<p>A cleaned and aggregated dataset with:</p>
<ul>
    <li><strong>Movie title</strong> (without year)</li>
    <li><strong>Genre</strong></li>
    <li><strong>Average rating</strong></li>
    <li><strong>Year of release</strong> (as integer)</li>
</ul>
<p>This prepares the data for further analysis, like trends over time, genre-based ratings, or recommendation systems.</p>

</body>
</html>
