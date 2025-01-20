Learning Spatial–Temporal EEG Representations in the Stiefel Manifold with Hilbert Transform

This repository implements an approach for mapping EEG signals onto the Stiefel manifold and using Hilbert-based transformations for feature extraction and classification. The method uses QR decomposition to preserve the orthogonality of EEG channels, applies Empirical Mode Decomposition (EMD) and the Hilbert Transform to capture instantaneous amplitude and phase, and finally uses a Convolutional Neural Network (CNN) to classify the transformed signals.

Joint work with Vida Jaberi
Key Highlights

Stiefel Manifold Mapping
We transform the EEG data onto the Stiefel manifold via QR decomposition, ensuring each channel’s columns remain orthonormal.
The geometry is preserved through Riemannian operations, e.g., tangent spaces and geodesic distances.
Hilbert-Huang Transform (HHT)
Empirical Mode Decomposition (EMD) splits signals into Intrinsic Mode Functions (IMFs).
Hilbert Transform then extracts instantaneous amplitude, phase, and frequency, providing fine-grained time-frequency analysis.
CNN Classification
A CNN is trained on manifold-aware features, with cross-entropy loss for classification.
Accuracy is used as the primary evaluation metric.
Workflow Overview

Preprocessing
Apply notch and band-pass filtering to remove noise.
Optionally select relevant EEG channels.
Stiefel Mapping
Perform QR decomposition on each trial to place data on the Stiefel manifold.
EMD + Hilbert Transform
Decompose signals into IMFs.
Use Hilbert Transform to get instantaneous features (amplitude, phase, frequency).
CNN Training & Evaluation
Train the CNN on the extracted features.
Use categorical cross-entropy as the loss function.
Evaluate final performance via accuracy.
Repository Contents

/src: Core scripts for preprocessing, manifold mapping, EMD/Hilbert, and CNN training.
/notebooks: Example Jupyter notebooks demonstrating data loading, transformations, and model training.
/docs: Additional resources detailing mathematical derivations on the Stiefel manifold.
Getting Started

Install Dependencies
pip install -r requirements.txt
Run Preprocessing & Manifold Mapping
Use preprocess.py to filter EEG data.
Run stiefel_map.py to compute QR decomposition.
Feature Extraction
Apply emd_hilbert.py to decompose signals and extract instantaneous features.
Train the CNN
Run train_cnn.py to train and evaluate the classifier on the extracted features.
Monitor accuracy and cross-entropy loss in TensorBoard.
Citation & Acknowledgments

If you use or modify this code, please cite:

Learning of Spatial–Temporal EEG Representation in the Stiefel Manifold Using Hilbert Transformation, in collaboration with Vida Jaberi
December 30, 2024
