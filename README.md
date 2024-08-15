# Skin Lesion Classification Challenge

## Project Overview
This repository contains the code and documentation for a skin lesion classification project completed as part of the IMA205 course (Apprentissage pour l'image et la reconnaissance d'objets) at Télécom Paris in May 2024.

## Challenge Description
The goal of this challenge was to classify dermoscopic images of skin lesions into eight different diagnostic classes using machine learning techniques. This project aimed to contribute to the early detection of skin cancer, particularly melanoma, through non-invasive computer-aided diagnosis (CAD) systems.

### Diagnostic Classes:
1. Melanoma
2. Melanocytic nevus
3. Basal cell carcinoma
4. Actinic keratosis
5. Benign keratosis
6. Dermatofibroma
7. Vascular lesion
8. Squamous cell carcinoma

## Dataset
The dataset consisted of 25,331 dermoscopic images of skin lesions, along with corresponding segmentation and metadata (age, sex, and anatomical position) when available. The data was split into a training-validation set (75%) and a test set (25%).

## Methodology

### Data Preprocessing
- Implemented data augmentation techniques, including ADASYN, to address class imbalance
- Handled missing metadata through imputation and placeholder values
- Applied segmentation using a modified ResNet architecture (MFSNet) for images lacking ground-truth segmentations

### Feature Extraction
- Utilized the ABCD rule (Asymmetry, Border, Color, Dimension) for manual feature extraction
- Employed advanced textural analysis techniques including Gray Level Co-occurrence Matrix (GLCM) and Weber Local Descriptor (WLD)

### Classification
- Tested Support Vector Machine (SVM) and Multilayer Perceptron (MLP) classifiers
- Selected MLP as the primary classifier due to its superior performance in handling non-linearities and high-dimensional data

## Results
- Public score: ~0.69
- Private score: ~0.678

## Future Improvements
- Refine feature extraction process
- Explore more sophisticated neural network architectures
- Expand the dataset with more varied examples

## Dependencies
- Numpy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Scikit-image
- SciPy
- Tensorflow
- Imblearn

## Author
Adnane El Bouhali

## Acknowledgements
This project was completed as part of the IMA205 course at Télécom Paris. Special thanks to Pietro Gori and Elsa Angelini for their guidance throughout the project.

## References
- [IEEE Article on Skin Lesion Classification](http://ieeexplore.ieee.org/document/918473/)
- [ScienceDirect Article on Dermoscopic Features](https://www.sciencedirect.com/science/article/pii/S0933365712001108#bib0180)
- [ScienceDirect Article on Skin Lesion Detection](https://www.sciencedirect.com/science/article/pii/S0957417416302354#bib0023)
- [ScienceDirect Article on Melanoma Detection](https://www.sciencedirect.com/science/article/pii/S0933365713001589)
- [Nature Article on Deep Learning for Skin Lesion Analysis](https://www.nature.com/articles/nature21056)
- [University of Bourgogne Document on Skin Lesion Segmentation](https://hal-univ-bourgogne.archives-ouvertes.fr/hal-01250955/document)
- [ISIC 2021 Workshop](https://workshop2021.isic-archive.com/)
- [ISIC 2020 Workshop](https://workshop2020.isic-archive.com/#paper)
- [ADASYN: Adaptive synthetic sampling approach for imbalanced learning](https://ieeexplore.ieee.org/document/4633969)
