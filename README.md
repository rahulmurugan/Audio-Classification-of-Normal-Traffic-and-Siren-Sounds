
# Audio Feature Analysis and Classification

## Introduction

This project focuses on distinguishing between emergency vehicle sirens and general road noise using AI-driven methods. The primary objective is to create models that classify audio segments into two categories: ambulance sirens and road noise. 

---

## Table of Contents

- [Requirements](#requirements)
  - [Files](#files)
  - [Packages](#packages)
- [Scripts Overview](#scripts-overview)
  - [Data Feature Analysis](#data-feature-analysis)
  - [Feature-Based Models](#feature-based-models)
  - [Spectrogram-Based Model](#spectrogram-based-model)
  - [Dataset Analysis](#dataset-analysis)
- [Datasets](#datasets)
- [Usage](#usage)
- [License](#license)

---

## Requirements

### Files
The following files and directories are required for the project:
- `Ambulance_final.csv`
- `Road_final.csv`
- `Spectro_Dataset/Spectro_train`
- `Spectro_Dataset/Spectro_Val`
- `Spectro_Dataset/Spectro_test`
- `Ambulance.wav`
- `Road.wav`

### Packages
Ensure you have the following Python packages installed:
- `Pandas`
- `Scipy`
- `Numpy`
- `Seaborn`
- `sklearn`
- `Matplotlib`
- `librosa`

---

## Scripts Overview

### Dataset Analysis
**File:** `Data_analysis.py`

This script analyzes the dataset of audio samples and their spectrograms. It includes:
- Bar charts comparing sample counts for two classes: **"Ambulance"** and **"Normal Traffic"**.
- Spectrogram visualizations for individual audio samples using `Librosa`.

These visualizations provide insights into class distribution and spectral features.

### Data Feature Analysis
**File:** `data_feature_analysis.py`

This script collects statistical metrics such as mean, median, and standard deviation for the dataset's audio features:
- 21 Mel Frequency Cepstral Coefficients (MFCCs)
- Roll-off rate
- Zero-crossing rate
- Spectral centroid
- Spectral bandwidth
- Chroma STFT

The script visualizes the features using:
- Bar graphs for audio feature log medians.
- Box plots for MFCC features with outliers removed.

### Feature-Based Models
**File:** `feature_based_models.py`

This script:
1. Visualizes, cleans, and normalizes the dataset.
2. Builds a Random Forest Classifier using hyperparameter tuning with grid and random search.
3. Generates plots for:
   - A single decision tree from the Random Forest model.
   - Feature importances for interpretability.
4. Constructs Dual & Primal SVC models.
5. Produces classification reports for all models.

### Spectrogram-Based Model
**File:** `Spectrogram.py`

This script leverages a **pre-trained ResNet-18 model** for binary classification of spectrogram images. Key steps include:
- Dataset preprocessing with transformations like resizing and normalization.
- Fine-tuning the ResNet-18 model in two training phases.
- Training with Binary Cross-Entropy Loss and the Adam optimizer.
- Evaluation using:
  - Accuracy metrics
  - Loss plots
  - A classification report
  - A confusion matrix
  - Visualizations for performance insights



---

## Datasets

The project utilizes large-scale audio datasets:
1. [Large-scale Audio Dataset](https://www.nature.com/articles/s41597-022-01727-2)
2. [Large-Scale Audio Dataset for Emergency Vehicle Sirens and Road Noises](https://figshare.com/articles/media/Large-Scale_Audio_Dataset_for_Emergency_Vehicle_Sirens_and_Road_Noises/19291472)

---

## Usage

1. Ensure all required files are in place.
2. Install the necessary Python packages listed in the [Requirements](#requirements) section.
3. Run the scripts in the following sequence for complete analysis:
   - `data_feature_analysis.py`
   - `feature_based_models.py`
   - `Spectrogram.py`
   - `Data_analysis.py`
4. Review the generated visualizations and classification reports for insights.

---

## License

This project is open-source. Please refer to the specific dataset licenses linked in the [Datasets](#datasets) section for terms of use.

---


