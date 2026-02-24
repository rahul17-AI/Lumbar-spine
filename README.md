# Lumbar-spine
This project uses a Gaussian Mixture Model (GMM) for unsupervised segmentation of lumbar spine MRI images and evaluates results using standard performance metrics. Lumbar Lordotic Angle (LLA) values are integrated to classify spinal curvature into Hyperlordosis, Hypolordosis, or Normal.

Project Overview:

This project implements an automated medical image analysis pipeline for lumbar spine MRI segmentation using a Gaussian Mixture Model (GMM), combined with Lumbar Lordotic Angle (LLA) based classification for spinal curvature assessment. The approach leverages unsupervised probabilistic clustering to segment anatomical structures without requiring labeled training data.
The system also performs quantitative evaluation against ground truth masks using widely accepted segmentation metrics, making it suitable for academic research, experimentation, and educational purposes in medical imaging and healthcare AI.

Objectives:

 -> Perform unsupervised segmentation of lumbar spine MRI images
 -> Evaluate segmentation accuracy using standard medical imaging metrics
 -> Integrate clinical measurement (LLA) for lordosis classification
 ->  Demonstrate practical use of probabilistic machine learning in healthcare

 Methodology / How It Works:

The pipeline follows these major steps:

1️. Image Acquisition
MRI images, ground truth masks, and optional pseudo images are uploaded.
Images may be grayscale or RGB.

2️. Preprocessing
Convert RGB images → grayscale
Normalize pixel intensities to [0, 1]
Flatten image into a feature vector for clustering

3️. Gaussian Mixture Model Segmentation
A Gaussian Mixture Model (GMM) is fitted on pixel intensities.
GMM assumes image intensities arise from multiple Gaussian distributions.
Each pixel is assigned to the most probable Gaussian component.
Output → Segmented image with multiple tissue clusters.

4️. Ground Truth Alignment
Ground truth masks are resized to match segmentation dimensions.
Binary thresholding ensures valid comparison.

5️. Performance Evaluation
The segmentation is validated using:
Accuracy Score
F1 Score (Macro)
Dice Coefficient
Jaccard Index (IoU)
Hausdorff Distance
These metrics capture both region overlap and boundary similarity.

6️. Lordosis Classification
Lumbar Lordotic Angle (LLA) values are read from an Excel sheet.
Classification rules:
LLA Range	Classification
LLA > 45°	Hyperlordosis
LLA < 20°	Hypolordosis
Otherwise	Normal

Technologies & Tools Used:
Programming Language:
-> Python

Libraries / Frameworks:

-> NumPy → Numerical computation
-> Matplotlib → Visualization
-> Scikit-image → Image processing
-> Scikit-learn → Gaussian Mixture Model
-> SciPy → Hausdorff distance computation
-> Pandas → Excel data handling

Environment:

-> Google Colab / Jupyter Notebook

Evaluation Metrics Explained:

-> Metric	Purpose
-> Accuracy	Pixel-wise correctness
-> F1 Score	Precision-Recall balance
-> Dice Coefficient	Overlap similarity
-> Jaccard Index (IoU)	Intersection over Union
-> Hausdorff Distance	Boundary deviation

Key Features:

✔ Unsupervised segmentation (no training dataset required)
✔ Probabilistic clustering via GMM
✔ Multi-metric validation framework
✔ Clinical measurement integration (LLA)
✔ Visual comparison of results

Why Gaussian Mixture Model (GMM)?

GMM provides:
-> Probabilistic soft clustering
-> Ability to model complex intensity distributions
-> Flexibility compared to K-Means
-> No requirement for labeled data

Applications:

-> Medical image analysis research
-> Educational demonstrations of ML in healthcare
-> Spine morphology studies
-> Computer-Aided Diagnosis (CAD) systems
-> Segmentation benchmarking experiments

Benefits & Advantages:

✔ No Labeled Training Data Required
Useful when annotated medical datasets are scarce.
✔ Robust Probabilistic Modeling
Handles intensity variation across MRI scans.
✔ Clinically Relevant Integration
Combines segmentation with diagnostic classification.
✔ Reproducible & Extensible
Easy to modify component count or thresholds.
✔ Multi-Perspective Evaluation
Uses both region-based and boundary-based metrics.

How to Run:

Open the notebook in Google Colab or Jupyter.

Upload:
-> MRI images
-> Ground truth masks
-> Excel file with LLA values
-> Execute cells sequentially.
-> View segmentation outputs & metrics.

Limitations:

-> Segmentation relies solely on pixel intensity (no spatial modeling)
-> Sensitive to number of Gaussian components
-> Does not incorporate deep learning features
-> Ground truth quality affects metric reliability

Possible Improvements:

-> Add spatial features (x, y coordinates)
-> Use advanced GMM variants or Bayesian GMM
-> Integrate deep learning segmentation (U-Net)
-> Add noise filtering & enhancement
-> Automate LLA extraction from images

Academic Relevance:

This project demonstrates fundamental concepts in:
-> Unsupervised Machine Learning
-> Probabilistic Modeling
-> Medical Image Segmentation
-> Quantitative Evaluation Metrics
-> Clinical Decision Support Systems
