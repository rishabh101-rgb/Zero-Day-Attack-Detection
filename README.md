# Zero-Day-Attack-Detection

# Unknown Attack Detection Using Feature Similarity

This project proposes an approach to detect completely unknown attack classes using deep learning and feature similarity techniques.

## Project Overview

- **Framework**: TensorFlow (for CNN model building and feature extraction)
- **Programming Language**: Python
- **Data**: Preprocessed from Excel files containing known and unknown attack classes
- **Core Idea**:  
  - Exclude one attack class from the training data to simulate an unknown attack.
  - Use a trained CNN to extract feature vectors for both known and unknown classes.
  - Apply cosine similarity to compare feature vectors.
  - Predict whether a sample belongs to a benign class or an attack class based on similarity scores.
  - Identify the closest known attack type (e.g., XSS, SQL Injection, etc.) for classified attacks.

## How It Works

1. **Data Preprocessing**:  
   - Load attack data from Excel files.
   - Normalize and clean data for training and feature extraction.

2. **Model Training**:  
   - Train a Convolutional Neural Network (CNN) on the dataset (excluding one attack class).
   - Extract feature vectors from the intermediate layers of the CNN.

3. **Feature Comparison**:  
   - Extract the feature vector of the excluded (unknown) class.
   - Use cosine similarity to compare the unknown class feature vector with known classes' feature vectors.

4. **Prediction**:  
   - If the similarity score crosses a certain threshold, classify the input as an attack.
   - Otherwise, classify it as benign.
   - For attacks, identify the closest matching known attack class.

## Requirements

- Python 3.x
- TensorFlow
- NumPy
- Pandas
- Scikit-learn
- Matplotlib (optional, for visualization)

You can install the dependencies using:

```bash
pip install tensorflow numpy pandas scikit-learn matplotlib
```

## Setup Instructions

1. Clone the repository.
2. Place your dataset (Excel files) inside the project directory.
3. Run the preprocessing script to prepare the dataset.
4. Train the CNN model using the provided training script.
5. Run the feature extraction and similarity comparison module to predict unknown attacks.

## Disclaimer

⚠️ This project is intended for **research and educational purposes** only. It should not be used in real-world security systems without extensive validation and testing.

