# VITS Model (Conditional Variational Autoencoder with Adversarial) for Audio Source Separation
## Overview
This repository contains the trained VITS (Variational Inference Transformer for Audio Source Separation) model, designed to perform high-quality audio source separation and text-to-speech synthesis. The model has been trained on 13,100 short audio clips spoken by a single speaker, totaling about 24 hours of audio, to produce a remarkable human-like voice effect.

Original authors: Jaehyeon Kim, Jungil Kong, and Juhee Son

Original Paper Link: https://arxiv.org/abs/2106.06103

## Data Collection

- **Total Clips**: 13,100
- **Total Duration**: ~24 hours
- **Audio Format**: 16-bit PCM
- **Sampling Rate**: 22 kHz
- **Dataset Split**:
  - Training Set: 12,500 samples
  - Validation Set: 100 samples
  - Test Set: 500 samples
- **Data Annotation**: Each file list contains the path to the audio file and the corresponding text.

## Pre-processing

### Text Preprocessing

- **Cleaning**: Irrelevant characters are removed.
- **Standardization**: Abbreviations replaced and numbers converted.

### Audio Pre-processing

- **Resampling**: Audio files are resampled to match the model's input requirements.
- **Feature Extraction**: Audio features such as Mel spectrograms are extracted using Short Time Fourier Transform (STFT).
- **Normalization**: Audio data is normalized to the range [-1, 1].

## Model Training

- **Learning Rate Decay**: Employed to improve convergence and stability.
- **Windowed Generator Training**: Reduces time and memory consumption without sacrificing quality.
- **Mixed Precision Training**: Utilizes half-precision floating point to increase training speed and reduce memory footprint.
- **Batch Size**: 4 (chosen based on computer performance)
- **Training Duration**: 48 hours

## Results

- **Model Performance**: As training progresses, the model captures more detailed information, improving the quality of the audio output.
- **Visualization**: TensorBoard is used for an intuitive visualization of training progress, showing enhancements in frame detail and overall audio quality.

## Inference

- **Sentence to Audio**: The model can successfully convert given sentences into audio files.
- **Output**: Audio files can be saved locally, demonstrating the model's ability to generate voices that are indistinguishable from real human voices.
