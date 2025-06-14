*Project Title*
***Audio Copy-Move Forgery Detection in Music Tracks***
Final Semester UG Project Submission – B.E. Computer Science and Engineering

*Project Summary:*
This project presents a method for detecting copy-move forgeries in music tracks, where a segment is duplicated and reinserted within the same audio. Unlike speech data, music presents unique challenges due to its harmonic structures and genre diversity.

To address this, the project proposes:

- Use of **Constant-Q Transform (CQT)** for spectrogram generation  
- Division into **seven octave-aligned subbands**  
- Extraction of **multi-domain features** (spectral, temporal, statistical, tonal)  
- Training a **1D Xception** deep learning model to classify audio as original or forged

*Key Features:*

- Dataset: 2,500 original instrumental music tracks from 10 diverse genres (Source: [Free Music Archive (https://freemusicarchive.org/))
- Realistic copy-move forgeries created through audio augmentation using `librosa`, `scipy`, and `pydub`
- Feature Extraction from CQT spectrograms segmented into octave subbands
- 1D Xception model using depthwise separable convolutions
- Achieved a test accuracy of 97.24% and an F1 Score of 0.9723

*Results:*
The proposed method using CQT spectrograms with octave subbanding and a 1D Xception model significantly outperformed the baseline STFT-based approach.

CQT vs STFT Performance Comparison
Feature Representation	Accuracy	F1 Score
CQT Subbands + Xception	97.24%	0.9723
STFT + Xception	78.83%	0.7858

CQT provides logarithmic frequency scaling, better capturing musical harmonics and tonal variations.

STFT suffers from limited resolution at low frequencies, making it less effective for detecting music forgeries.

The CQT-based model demonstrated consistent performance across all 10 music genres, confirming its robustness and generalization ability.

Genre-Wise Performance
Genre	Accuracy	F1 Score
Classical	97.37%	0.9730
Country	98.68%	0.9867
Electronic	94.74%	0.9474
Folk	96.05%	0.9600
Hip Hop	98.68%	0.9870
Jazz	96.05%	0.9610
Old Historic	98.68%	0.9867
Pop	94.74%	0.9474
Rock	98.68%	0.9870
Soul R&B	98.68%	0.9867

These results confirm that CQT with subband features is better suited for music-based audio forgery detection than traditional STFT.
