# Music Genre & Mood Classification for Personalized Playlist Generation

Machine learning and deep learning project for **music genre and mood classification** and **automatic playlist generation**, developed at **Télécom Paris** as part of a team of five.

The project combines **audio feature extraction, classical machine learning, deep learning and API-based music recommendation** to build a personalized playlist generation system.

## Overview

The goal of the project was to explore how machine learning can be used to automate tasks traditionally performed through music signal processing and recommendation systems.

The project covers three main components:

1. **Music genre classification**
2. **Music mood classification**
3. **Personalized playlist generation**

A companion **Android application** was also developed to provide a user-facing interface for the system.

## Machine Learning Pipeline

### Music Genre Classification

Several audio features were extracted from music tracks, including:

- MFCCs
- RMS energy
- Spectral centroid
- Spectral bandwidth
- Spectral contrast
- Spectral flatness
- Spectral rolloff
- Tonnetz
- Zero-crossing rate
- Tempo

Statistical descriptors such as means and standard deviations were then used to build feature vectors for classification.

Several classical machine learning models were explored and compared:

- Random Forest
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)
- Logistic Regression
- Gradient Boosting

### Deep Learning

The project also explored deep learning approaches based on **audio spectrograms**.

```text
Audio
  ↓
Spectrogram generation
  ↓
Image preprocessing
  ↓
CNN / VGG16
  ↓
Genre classification
```

This provides an alternative to the manually engineered audio-feature approach used by the classical machine learning models.

## Mood Classification

The project also investigates **music mood classification**.

The system considers several mood categories, including:

- Dark
- Deep
- Dream
- Emotional
- Epic
- Happy
- Motivational
- Relaxing
- Romantic
- Sad

These mood predictions can then be used as an input for playlist generation.

## Automatic Playlist Generation

The classification models are integrated into a playlist generation pipeline.

A playlist can be generated according to different types of input, such as:

- A desired **mood**
- A **music genre**
- A **reference song**
- A combination of musical characteristics

The system can then retrieve appropriate tracks through the **Deezer API**.

The project also includes a natural-language mood input component using **zero-shot classification with `facebook/bart-large-mnli`**, allowing a textual description to be mapped to one of the predefined mood categories.

Example:

```text
"I'm looking for something energetic and uplifting"
                         ↓
                  Mood prediction
                         ↓
                    Happy / Epic
                         ↓
                Playlist generation
                         ↓
                    Deezer API
```

## Android Application

An Android application was developed as the user-facing component of the project.

It provides an interface through which users can interact with the playlist generation system and access the project's music recommendation functionalities.

The Android source code is included in the repository under:

```text
AndroidStudio/
```

## Project Structure

```text
music-playlist-generation/
│
├── AndroidStudio/                 # Android application
│
├── ClassificateurGenre/
│   ├── CNN/                      # CNN / spectrogram-based models
│   └── MachineLearning/          # Classical ML models
│
├── DossierData/                  # Data and trained models
│
├── GenreMoodClassification.py    # Genre & mood classification
├── CnnClassification.py          # CNN classification pipeline
├── playlistGeneration.py         # Playlist generation
├── phraseMood.py                 # Natural-language mood classification
├── api.py                        # API-related functionality
│
├── organisation/                 # Project documentation
├── SUIVI.md                      # Project tracking
│
└── README.md
```

Large datasets and trained models are not necessarily included in the repository. See the relevant project directories for details.

## Technologies

**Programming & Data**

- Python
- Pandas
- NumPy

**Machine Learning**

- Scikit-learn
- Random Forest
- SVM
- KNN
- Logistic Regression
- Gradient Boosting

**Deep Learning**

- TensorFlow / Keras
- CNN
- VGG16

**Audio Processing**

- Librosa
- Spectrograms
- MFCCs and spectral features

**NLP**

- Hugging Face Transformers
- BART
- Zero-shot classification

**Application & APIs**

- Android
- Deezer API

## My Contribution

As part of the five-person team, my main contribution focused on the **machine learning component of the music classification pipeline**.

I worked particularly on:

- Development and evaluation of a **Random Forest classifier** for music genre classification
- Audio data preparation and feature extraction
- Construction and evaluation of machine learning pipelines
- Comparison of different classification approaches
- Feature extraction optimization, including parallel processing
- Model benchmarking and performance analysis

The project gave me hands-on experience with the complete pipeline from **raw audio data and feature engineering to machine learning models and an end-user application**.

## Academic Context

**Télécom Paris — Engineering Project**

Team of 5  
2025

The project combines **machine learning, deep learning, audio processing and recommendation systems** to explore practical applications of AI to music.

## Project Report

The detailed project report is available in the [`report/`](report/) directory.
