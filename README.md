# Movie Recommendation System using Machine Learning

## Project Overview
This project is a **Content-Based Movie Recommendation System** built using Machine Learning and Python. The system suggests movies to a user based on their similarity to a specific movie provided as input. It utilizes natural language processing (NLP) to analyze movie metadata and calculates similarity scores between movies to provide the best recommendations.

## Dataset
The dataset used in this project is stored in the `movies.csv` file. It contains comprehensive details about various movies. For the purpose of content-based filtering, this project focuses on the following key features:
- `genres`
- `keywords`
- `tagline`
- `cast`
- `director`

## Tech Stack & Libraries
- **Language:** Python
- **Environment:** Jupyter Notebook
- **Data Manipulation:** `pandas`, `numpy`
- **Machine Learning & NLP:** `scikit-learn` (`TfidfVectorizer`, `cosine_similarity`)
- **String Matching:** `difflib` (built-in library, used to find the closest matching movie title to the user's input)

## How it Works
1. **Data Preprocessing**: Relevant textual features (`genres`, `keywords`, `tagline`, `cast`, `director`) are extracted from the dataset. Missing or null values are imputed with empty strings to prevent errors during processing.
2. **Feature Combination**: The selected text features are combined into a single string for each movie.
3. **Text Vectorization**: The combined text data is transformed into numerical feature vectors using the `TfidfVectorizer` from `scikit-learn`.
4. **Similarity Calculation**: The system employs `cosine_similarity` to measure the mathematical similarity between the feature vectors of all movies in the dataset.
5. **Recommendation Generation**: 
   - The user is prompted to input the name of their favorite movie.
   - `difflib.get_close_matches` is used to identify the closest actual movie title in the dataset, accounting for potential typos.
   - The system retrieves the pre-calculated similarity scores of all other movies relative to the selected movie.
   - The movies are ranked in descending order based on their similarity scores, and the top recommendations are displayed to the user.

