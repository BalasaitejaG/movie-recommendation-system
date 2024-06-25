# Movie Recommendation Engine

This project is a movie recommendation engine that processes a movie dataset and provides various recommendation functionalities based on genres, similar movies, and movie release years.

## Features

- **Data Cleaning:** Removes unnecessary columns and handles missing values.
- **Genre-Based Recommendation:** Recommends movies based on similar genres.
- **Movie-Based Recommendation:** Recommends movies similar to a given movie.
- **Random Movie Picker:** Picks a random movie title from the dataset.
- **Year-Based Recommendation:** Recommends top movies based on their release year.

## Requirements

- Python 3.x
- numpy
- pandas
- matplotlib
- seaborn
- ipywidgets
- IPython
- mlxtend

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/your_username/movie-recommendation-engine.git
    ```
2. Change to the project directory:
    ```sh
    cd movie-recommendation-engine
    ```
3. Install the required packages:
    ```sh
    pip install -r requirements.txt
    ```

## Usage

1. Ensure you have the `movie_metadata.csv` file in the project directory.
2. Run the script:
    ```sh
    python x.py
    ```

## Data Processing

- Reads the dataset from `movie_metadata.csv`.
- Removes unnecessary columns such as `color`, `director_facebook_likes`, etc.
- Combines actor names into a single column.
- Handles missing values in the `gross` and `budget` columns.

## Recommendation Functions

### Genre-Based Recommendation

```python
def recommendation_genres(gen):
    gen = genres[gen]
    similar_genres = genres.corrwith(gen)
    similar_genres = similar_genres.sort_values(ascending=False)
    similar_genres = similar_genres.iloc[1:]
    return similar_genres.head(3)

