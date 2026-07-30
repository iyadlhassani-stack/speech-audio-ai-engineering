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

## Repository structure

```text
.
├── notebooks/
│   ├── 01_audio_basics.ipynb
│   └── 02_spectrograms_and_mel_features.ipynb
├── audio_samples/
├── outputs/
├── src/
└── README.md
```

## Technologies

* Python
* Jupyter Notebook
* NumPy
* Matplotlib
* SoundFile
* Librosa

## Goal

The goal of this repository is to build a strong practical foundation in speech and audio processing before moving toward modern Speech AI systems such as speech recognition, speaker analysis and voice generation.

