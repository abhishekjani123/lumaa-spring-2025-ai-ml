# Movie Recommendation System using TF-IDF and cosine similarity

This repository contains a Python-based recommender system that utilizes TF-IDF, cosine similarity, and additional heuristics (genre matching and setting detection) to suggest movies based on user input.

## Overview

The **Movie Recommender** is designed to:
1. Parse a movie dataset (e.g., *imdb_top_1000.csv*)
2. Generate weighted text features for each movie (including repeated genres and overviews).
3. Use **TF-IDF vectorization** to calculate baseline similarity among movies.
4. **Extract genres** from user input via a customizable dictionary of synonyms.
5. Account for user interest in specific *settings* (e.g., “space,” “medieval,” etc.) to refine recommendations.
6. Return top movie suggestions based on a **composite similarity score** blending TF-IDF, genre matching, and setting matching.


## Features

- **Genre Synonym Recognition**: Maps multiple user expressions (e.g., “scifi,” “science fiction,” “sf”) to the canonical genre `sci-fi`.
- **Weighted Feature Engineering**: Gives more importance to genres and overviews (repetition in the text) for better alignment with user preferences.
- **Setting Detection**: Boosts recommendations if a movie’s overview matches the user’s desired setting (e.g., “space,” “future,” “historical”).
- **Composite Scoring**: 
  - TF-IDF Similarity (40%)
  - Genre Match (30%)
  - Setting Match (30%)

## Video:

https://github.com/user-attachments/assets/c06856dc-6aeb-4bb4-9a5e-8aac87b1571c

## Data

By default, this project references an **IMDb-style dataset** named `imdb_top_1000.csv`.  
- **Columns Expected**: `Series_Title`, `Released_Year`, `Genre`, `Overview`, `Director`, `Star1`, `Star2`, `IMDB_Rating`, etc.  


## Running:

1. **Open the notebook**:
   - **Google Colab**:
     - Upload your `.ipynb` file to [Colab](https://colab.research.google.com/).
     - Alternatively, if your notebook is on GitHub, open it directly by replacing `github.com` with `colab.research.google.com/github` in your browser’s address bar.
   - **Jupyter Notebook**:
     - Run `jupyter notebook MovieRecommender.ipynb` in your terminal (ensure Jupyter is installed).

2. **Upload or place the CSV**:
   - In **Google Colab**, you can upload the CSV via the *Files* panel, or mount Google Drive:
     ```python
     from google.colab import drive
     drive.mount('/content/drive')
     ```
     Then copy or move the CSV into your Colab workspace.
   - In **Jupyter Notebook**, simply place the CSV file in the same folder as your `.ipynb` (or specify the correct path).

3. **Run all cells** from top to bottom:
   - This will import libraries, initialize the recommender class, and set up everything required.

4. Enter your Movie Description and get the Recommendations.
  
 ## Output:

```python
Enter your movie preferences: I love action and science fiction movies.

Recommendations for: 'I love action and science fiction movies.'

1. Captain America: Civil War (2016) - Action, Adventure, Sci-Fi
   Rating: 7.8
   Similarity Score: 0.315
   Overview: Political involvement in the Avengers' affairs causes a rift between Captain America and Iron Man....

2. Serenity (2005) - Action, Adventure, Sci-Fi
   Rating: 7.8
   Similarity Score: 0.315
   Overview: The crew of the ship Serenity try to evade an assassin sent to recapture one of their members who is telepathic....

3. Edge of Tomorrow (2014) - Action, Adventure, Sci-Fi
   Rating: 7.9
   Similarity Score: 0.314
   Overview: A soldier fighting aliens gets to relive the same day over and over again, the day restarting every time he dies....

4. Predator (1987) - Action, Adventure, Sci-Fi
   Rating: 7.8
   Similarity Score: 0.314
   Overview: A team of commandos on a mission in a Central American jungle find themselves hunted by an extraterrestrial warrior....

5. Rogue One (2016) - Action, Adventure, Sci-Fi
   Rating: 7.8
   Similarity Score: 0.313
   Overview: The daughter of an Imperial scientist joins the Rebel Alliance in a risky move to steal the plans for the Death Star....
```

### Expected Salary: 4000 $ per Month

