# ML Project: Mood Classification & Recommendation System

This repository contains the code and resources for the **Mood Classification and Recommendation System** project. The project classifies user mood from their journal input and provides personalized activity recommendations based on the identified mood.

## Project Overview

The project includes two main components:
1. **Mood Classification**: A machine learning model that classifies user mood from text input into five categories: **Anger**, **Happy**, **Sadness**, **Fear**, and **Love**.
2. **Recommendation System**: A system that suggests personalized activities based on the user's classified mood.

## Project Structure

The project is organized as follows:

1. **ML Classification Model Folder**  
   - Dataset: The preprocessed and cleaned dataset used for model training.
   - Model Training Notebook: Jupyter notebook for training and evaluating the ML model.
   - Saved Model Weights: The trained model weights after completing the training process.
  
2. **Feature Extraction (TF-IDF) Folder**  
   - Transformed Features: Files containing the transformed features using TF-IDF.
   - Pickle/PKL: The preprocessed tokenizer or transformer object used in feature extraction, which can be reused for new data.

3. **Recommendation System Folder**  
   - Recommendation System Notebook: Jupyter notebook used for generating personalized activity recommendations based on the user's mood (using the GRU Model).
   - Recommendation Data (JSON): Predefined mood-to-activity mappings and configurations for the recommendation system.

## Model Details: Mood Classification

### Model Overview
- The **Mood Classification Model** uses text input to classify the user's mood into one of five categories: **Anger**, **Happy**, **Sadness**, **Fear**, **Love**.
- The model is trained using the **TF-IDF** features extracted from the preprocessed dataset, which represents the text in a numerical format for model input.
- The model is implemented using **TensorFlow** with a **GRU** (Gated Recurrent Unit) architecture, which is suitable for processing sequential data like text.

### Model Performance
- The model's performance is evaluated using accuracy, precision, recall, and F1-score for each class.
- The model has been fine-tuned to ensure reliable classification across all five classes, especially for the minority classes.

### Model File
- **trained_model.h5**: The saved model weights after training.

## Recommendation System Details

### System Overview
- The **Mood-Based Recommendation System** suggests activities to users based on their classified mood (Anger, Happy, Sadness, Fear, Love).
- Recommendations are categorized into three mood levels:
  - **High Mood**: Activities for users in a positive or energetic mood (e.g., socializing, exercise).
  - **Medium Mood**: Activities for users in a neutral mood (e.g., relaxation, meditation).
  - **Low Mood**: Activities for users in a low energy or stressed mood (e.g., calming exercises, self-care).

### Recommendation Process
1. The user's mood is classified using the **Mood Classification Model**.
2. Based on the mood classification, appropriate activity suggestions are retrieved from the **recommendations.json** file.
3. The system also tailors the suggestions based on the time of day (morning, afternoon, evening, or night).

### Recommendation File
- **recommendations.json**: Contains predefined mood-to-activity mappings with suggestions for different moods and times of day.

## Files in Detail

### ML Classification Model Folder
- **preprocessed_data.csv**: The cleaned dataset used for training the model.
- **model_training.ipynb**: Jupyter notebook containing the model training, evaluation, and hyperparameter tuning steps.
- **trained_model.h5**: The saved model weights after training.

### Feature Extraction (TF-IDF) Folder
- **tfidf_features.npz**: TF-IDF features extracted from the preprocessed dataset.
- **tfidf_transformer.pkl**: The saved transformer object used for extracting TF-IDF features.

### Recommendation System Folder
- **recommendation_system.ipynb**: Jupyter notebook for generating personalized activity recommendations based on mood.
- **recommendations.json**: Contains predefined mood-to-activity mappings categorized by mood levels and time of day.
