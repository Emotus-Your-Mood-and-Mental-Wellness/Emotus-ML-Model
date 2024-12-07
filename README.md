# ML Project: Mood Classification & Recommendation System
This repository contains the code and resources for the Mood Classification and Recommendation System project. The project classifies user mood from their journal input and provides personalized activity recommendations based on the identified mood.

## Project Overview
The project includes two main components:
1. A machine learning model that classifies user mood from text input into five categories: **Anger**, **Happy**, **Sadness**, **Fear**, and **Love**.
2. A system that suggests personalized activities based on the user's classified mood.

## About Dataset

The dataset used in this project contains user input texts (tweets) labeled into five distinct mood categories. This dataset was specifically chosen because it focuses on text data written in **Indonesian**, making it highly relevant for the project's target audience. It captures diverse emotional expressions commonly found in social media posts, providing a realistic and practical foundation for building a mood-based journaling and recommendation system. Informal text, slang, and diverse emotional expressions are common in social media, making the dataset both challenging and practical for real-world applications. Working with Indonesian text highlights the need for tailored text preprocessing techniques, such as stemming using the Sastrawi library and removing stopwords common in Bahasa Indonesia.

- **Total Samples:** 4401
- **Columns:**
  - **`label`**: The mood category for the text (anger, happy, sadness, fear, love).
  - **`tweet`**: The original user input text.
  - **`refined_tweet`**: The preprocessed version of the user input text, used for feature extraction and modeling.

### Class Distribution
The dataset has the following class distribution, represented as percentages of the total dataset:

| Label   | Proportion (%) |
|---------|----------------|
| Anger   | 25.02         |
| Happy   | 23.11         |
| Sadness | 22.65         |
| Fear    | 14.75         |
| Love    | 14.47         |

Sample entries from the dataset:

| Label   | Refined Tweet                     |
|---------|-----------------------------------|
| Anger   | "kesal banget hari ini gak karuan"|
| Happy   | "seneng banget dapat kabar baik"  |
| Sadness | "sedih rasanya kehilangan dia"    |
| Fear    | "takut banget ngeliat berita itu" |
| Love    | "cinta ini tak akan pernah padam" |

### Addressing Class Imbalance
To mitigate the effects of class imbalance, specific techniques were employed during the feature extraction and model training processes. During model training, strategies such as using **class weights** to give higher importance to minority classes like **fear** and **love**, helping the model learn from limited data for these labels.



## Project Structure
1. **ML Classification Model Folder**  
   - The preprocessed and cleaned dataset used for model training.
   - Jupyter notebook for training and evaluating the ML model.
2. **Recommendation System Folder**  
   - Jupyter notebook used for generating personalized activity recommendations based on the user's mood (using the GRU Model).
   - Contains predefined mood-to-activity mappings with suggestions for different moods and times of day (JSON.file).

## Model Details: Mood Classification
### Model Overview
- The Classification model uses text input to classify the user's mood into one of five categories: **Anger**, **Happy**, **Sadness**, **Fear**, **Love**.
- The model is trained using the TF-IDF features extracted from the preprocessed dataset, which represents the text in a numerical format for model input.
- The model is implemented using TensorFlow with GRU (Gated Recurrent Unit) architecture, which is suitable for processing sequential data like text.
### Model Performance
- The model's performance is evaluated using accuracy, precision, recall, and F1-score for each class.
- The model has been fine-tuned to ensure reliable classification across all five classes, especially for the minority classes.

## Recommendation System Details
The Mood-Based Recommendation System suggests activities to users based on their classified mood (Anger, Happy, Sadness, Fear, Love).
Recommendations are categorized into three mood levels:
  - **High Mood**: Activities for users in a positive or energetic mood
  - **Medium Mood**: Activities for users in a neutral mood 
  - **Low Mood**: Activities for users in a low energy or stressed mood
### Recommendation Process
1. The user's mood is classified using the Mood Classification Model.
2. Based on the mood classification, appropriate activity suggestions are retrieved from the recommendations.json file.
3. The system also tailors the suggestions based on the time of day (morning, afternoon, evening, or night).

