# Investigating Netflix Movies

## Contents

- `netflix_data.csv` - The dataset used for this analysis.

- `notebook.ipynb` - My completed notebook from DataCamp.

## Project Instructions

Perform exploratory data analysis on the `netflix_data.csv` data to understand more about movies from the 1990s decade.

- What was the most frequent **movie** duration in the 1990s? Save an approximate answer as an integer called `duration` (use 1990 as the decade's start year).

- A movie is considered short if it is less than 90 minutes. Count the number of **short action movies** released in the 1990s and save this integer as `short_movie_count`.

Feel free to experiment after submitting the project!

## Code Snippet

```python
#1a Select the 1990s with boolean operators
import numpy as np
df_90 = netflix_df[np.logical_and(netflix_df['release_year'] >= 1990, netflix_df['release_year'] <= 1999)]

#1b Select the 1990s with .between()
df_90 = netflix_df[netflix_df['release_year'].between(1990, 1999)]

#1c Select the 1990s with &
df_90 = netflix_df[(netflix_df['release_year'] >= 1990) & (netflix_df['release_year'] <= 1999)]

#2 Select movies only
df_90 = df_90[netflix_df['type'] == "Movie"]

#3a Most frequent duration with .mode()
duration = df_90['duration'].mode()[0]

#3b Most frequent duration with .value_counts()
duration = df_90['duration'].value_counts().index[0]

print("The most frequent movie duration in the 1990s was " + str(duration) + " minutes.")
```
