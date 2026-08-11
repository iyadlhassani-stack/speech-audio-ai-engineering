# Speech & Audio AI Engineering

This repository documents my progressive learning of speech and audio AI engineering through practical Jupyter notebooks.

## Current progress

### 01 — Audio Fundamentals

The first notebook covers:

* loading WAV audio files;
* inspecting sample rate and audio shape;
* detecting mono and stereo audio;
* converting stereo audio to mono;
* calculating audio duration;
* waveform visualization;
* amplitude and clipping inspection;
* resampling audio to 16 kHz;
* comparing original and resampled signals;
* frequency analysis with the FFT;
* Nyquist frequency.

### 02 — Spectrograms and Mel Features

The second notebook covers:

* selecting a short audio excerpt;
* resampling speech audio to 16 kHz;
* defining 25 ms analysis windows and a 10 ms hop length;
* computing the Short-Time Fourier Transform;
* extracting the STFT magnitude;
* converting magnitude values to decibels;
* visualizing a classical spectrogram;
* computing an 80-band Mel-spectrogram;
* converting the Mel-spectrogram to log-Mel;
* visualizing the log-Mel spectrogram;
* comparing classical and Mel frequency representations.

## Audio processing pipeline

```text
Waveform
→ resampling
→ framing
→ STFT
→ magnitude
→ spectrogram
→ Mel filter bank
→ Mel-spectrogram
→ log-Mel spectrogram
```
### 03 — Audio Classification with ESC-50

The third notebook builds a complete audio classification baseline using a real-world subset of the ESC-50 dataset.

It covers:

- exploring ESC-50 metadata;
- selecting five balanced sound classes;
- loading and listening to real audio samples;
- resampling audio to 16 kHz;
- extracting 13 MFCC coefficients;
- converting variable-length MFCC sequences into fixed 26-feature vectors;
- splitting train and test sets using the official ESC-50 folds;
- standardizing features without data leakage;
- training a k-nearest neighbors classifier;
- evaluating the model with accuracy, a confusion matrix, precision, recall and F1-score;
- inspecting misclassified audio examples.

The baseline achieved 75% accuracy on the held-out test fold.

### 04 — Audio Classification Improvements

The fourth notebook improves the previous ESC-50 baseline by introducing richer features and more rigorous evaluation.

It covers:

- extracting MFCC, delta MFCC and delta-delta features;
- representing each audio file with 78 features;
- evaluating several values of `k`;
- using the five official ESC-50 folds;
- comparing k-NN and SVM classifiers;
- measuring mean accuracy, standard deviation and macro F1;
- analyzing model performance fold by fold.

The best k-NN configuration used `k = 3` and achieved:

- 78.0% mean accuracy;
- 2.92% standard deviation.

The SVM with an RBF kernel achieved:

- 84.5% mean accuracy;
- 84.27% mean macro F1;
- 5.79% standard deviation.

The SVM became the strongest classical baseline in the repository.
## 05 — Speech Recognition (ASR)

This notebook introduces automatic speech recognition and builds a complete ASR evaluation pipeline.

### Topics covered

- CTC decoding and blank tokens
- Greedy decoding
- Word Error Rate (WER)
- Text normalization
- Audio resampling to 16 kHz
- Pretrained ASR with Whisper Tiny
- Reference vs predicted transcription
- Word-level error alignment
- Substitutions, deletions and insertions
- Error visualization and analysis

### Experiment

A 19-second French speech excerpt was transcribed using `openai/whisper-tiny`.

Results:

- WER: **26.47%**
- Substitutions: **7**
- Deletions: **2**
- Insertions: **0**

The main recognition difficulties involved proper nouns, rare vocabulary and phonetically ambiguous sequences.

## Repository structure

```text
```text
speech-audio-ai-engineering/
│
├── notebooks/
│   ├── 01_audio_basics.ipynb
│   ├── 02_spectrograms_and_mel_features.ipynb
│   ├── 03_audio_classification.ipynb
│   ├── 04_audio_classification_improvements.ipynb
│   └── 05_speech_recognition_asr.ipynb
│
├── audio_samples/
│   └── Local audio files used for experiments
│
├── data/
│   └── ESC-50 dataset (excluded from Git)
│
├── outputs/
│   └── Generated outputs and experiment results
│
├── src/
│   └── Reusable source code and utilities
│
├── .gitignore
└── README.md
```

## Technologies

Core
Python
Jupyter Notebook
NumPy
Pandas
Matplotlib
Audio Processing
Librosa
Waveform analysis
Audio resampling
FFT
STFT and spectrograms
Mel spectrograms
MFCCs
Delta and delta-delta features
Machine Learning
scikit-learn
StandardScaler
k-Nearest Neighbors (kNN)
Support Vector Machines (SVM)
Cross-validation
Accuracy and Macro F1
Confusion matrices
Speech Recognition
Hugging Face Transformers
PyTorch
OpenAI Whisper Tiny
Automatic Speech Recognition (ASR)
CTC decoding concepts
Greedy decoding
Text normalization
Word Error Rate (WER)
Word-level error alignment
Substitution, deletion and insertion analysis
Development Tools
Git
GitHub
Python virtual environments (venv)
## Goal

The goal of this repository is to build a strong practical foundation in speech and audio processing before moving toward modern Speech AI systems such as speech recognition, speaker analysis and voice generation.

