# ML Project: Mood Classification & Recommendation System
This repository contains the code and resources for the Mood Classification and Recommendation System project. The project classifies user mood from their journal input and provides personalized activity recommendations based on the identified mood.

## Project Overview
The project includes two main components:
1. A machine learning model that classifies user mood from text input into five categories: **Anger**, **Happy**, **Sadness**, **Fear**, and **Love**.
2. A system that suggests personalized activities based on the user's classified mood.

## Project Structure
1. **ML Classification Model Folder**  
   - The preprocessed and cleaned dataset used for model training.
   - Jupyter notebook for training and evaluating the ML model.
   - The trained model weights after completing the training process.
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

