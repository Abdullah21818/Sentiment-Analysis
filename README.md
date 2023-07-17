# Emotion Classification from Audio Signals

This project aims to predict the emotion associated with an audio signal using Mel spectrogram and chromagram features. The classifier will be an SVM implemented from scratch. We will also apply a PCA technique for dimensionality reduction.

## Background

Audio signal representations such as Mel spectrograms and chromagrams are key in understanding the content of the audio. A Mel spectrogram is a frequency-based representation of an audio signal that involves fragmenting the signal into several windows, applying a Fourier Transform to identify the frequency components, and computing the amplitudes of the different frequencies [[1]](https://librosa.org/doc/main/generated/librosa.feature.melspectrogram.html). Chromagrams are another related representation that characterizes the pitch profile of a signal according to the twelve pitch classes used in music [[1]](https://librosa.org/doc/main/generated/librosa.feature.melspectrogram.html).

Here are some examples of the different components invovled in this:


## Dataset

We use the Ryerson Audio-Visual Database of Emotional Speech and Song, which includes 1440 audio files vocalized by 24 professional actors [[2]](https://zenodo.org/record/1188976#.Y3qkx3bMLIU). The files are named according to several identifiers like modality, vocal channel, emotion, emotional intensity, statement, repetition, and actor. For this project, we only consider the emotions: “calm”, “happy”, “angry”, and “fearful” and categorize them into two broad classes: positive (“calm” and “happy”) and negative (“angry” and “fearful”).

## Approach

We follow two steps for classification:

1. **SVM Classifier**: We use an SVM classifier to predict whether a given audio signal conveys a positive or negative emotion. We implement SVM from scratch using gradient descent on a cost function that allows handling non-linearly separable data.

2. **PCA-based SVM Classifier**: We use Principal Component Analysis (PCA) for dimensionality reduction of the original data, and then repeat the steps of SVM classification on the low-dimensional representation.

Both the approaches include computing the classification accuracy for both the training and testing subsets to evaluate our models.

## Requirements

Python 3.x along with the following Python libraries is required to run the project:
1. numpy
2. scipy
3. librosa
4. matplotlib

To install these libraries, use the following pip command:
