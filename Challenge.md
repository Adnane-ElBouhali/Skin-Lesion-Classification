# Skin Lesion Classification Challenge

## Description

### Introduction
A skin lesion is defined as a superficial growth or patch of the skin that is visually different and/or has a different texture than its surrounding area. Skin lesions, such as moles or birthmarks, can degenerate and become cancerous, with melanoma being the deadliest skin cancer. Its incidence has increased during the last decades, especially in regions predominantly populated by white people.

The most effective treatment is early detection followed by surgical excision. Therefore, several approaches for skin cancer detection have been proposed in recent years, including non-invasive computer-aided diagnosis (CAD) systems.

### Goal of the Challenge
The goal of this challenge is to classify dermoscopic images of skin lesions into eight different diagnostic classes:
1. Melanoma
2. Melanocytic nevus
3. Basal cell carcinoma
4. Actinic keratosis
5. Benign keratosis
6. Dermatofibroma
7. Vascular lesion
8. Squamous cell carcinoma

To achieve this, you will extract features such as Asymmetry, Border irregularity, Colour, and Dimension of the lesion (commonly referred to as the ABCD rule). Following feature extraction, you will apply machine learning algorithms to classify the images.

## Data
The dataset consists of 25,331 dermoscopic images of skin lesions, along with their corresponding segmentation and metadata (age, sex, and anatomical position) when available. The data has already been randomly split into a training-validation set (75%) and a test set (25%). You are provided with the classification (done by clinicians) of the training-validation set, and your task is to correctly classify each dermoscopic image in the test set.

**Note:** You are only allowed to use the data provided in this challenge.

## Feature Extraction
You are free to use any features you'd like. A list of references describing well-known features is provided at the end of this page, but you can find many more articles in the literature. Use Pubmed, Google Scholar, or simply Google to find them. By using the network of Télécom Paris or its VPN, you will automatically have access to most scientific journals. If you encounter any difficulties, feel free to contact [Pietro Gori](mailto:pietro.gori@telecom-paris.fr).

## Evaluation

### Challenge Evaluation
The evaluation of the challenge will be based on:
1. The ranking in the leaderboard (both private and public).
2. A report.
3. The quality of your code.

The student with the best ranking in the private leaderboard at the end of the challenge will receive between 2 and 4 extra points on their final grade, depending on their result.

You will need to submit a report thoroughly explaining the feature extraction process, the classification algorithms used, why you chose them, and any pre- and post-processing steps. Be careful! You will be penalized if your report simply lists results without proper analysis, such as "I tried this algorithm but it did not work, so I tried another one," etc.

### Code Submission
You must write proper, well-commented, and clean code in Python 3. I will test your code, and if it does not work, you will incur a penalty on your grade. Please specify the version of the libraries used at the beginning of your code. You can write a set of functions with a main one—I will only run the main function—or a Jupyter Notebook.

Everything, including the report and code, must be uploaded to E-campus in the Challenge section before the deadline.

### Metrics
The ranking metric used will be the Weighted Categorization Accuracy, defined as:

\[ WA = \frac{1}{N} \sum_{i=1}^{N} w_i I(y_i = f_i) \]

such that

\[ \sum_{i=1}^{N} w_i = N \]

to keep the maximum value equal to 1.

Where \( y_i \) are ground truths, \( f_i \) are the predicted results, and \( w_i \) are the weights of the \(i\)-th test image. Assuming we have \( K \) groups—or classes—denoted as \( G = \{G_1, \dots, G_K\} \) and we assign the same weight \( w_t \) to all images of the same group \( t \), the weights are calculated as:

\[ w_t = \frac{N}{k |G_t|} \]

This allows us to account for any imbalances in the dataset.

The class weights in the test set are as follows:
\[ [ 0.7005531, 0.24592265, 0.95261733, 3.64804147, 1.20674543, 13.19375, 12.56547619, 5.04219745 ] \]

## Methods
You must use Python 3 as the programming language. I strongly suggest using `numpy` and `scikit-learn`.

You are allowed to use any pre-processing and post-processing techniques, whether coded by you or correctly referenced in the report.

## References
- [IEEE Article on Skin Lesion Classification](http://ieeexplore.ieee.org/document/918473/)
- [ScienceDirect Article on Dermoscopic Features](https://www.sciencedirect.com/science/article/pii/S0933365712001108#bib0180)
- [ScienceDirect Article on Skin Lesion Detection](https://www.sciencedirect.com/science/article/pii/S0957417416302354#bib0023)
- [ScienceDirect Article on Melanoma Detection](https://www.sciencedirect.com/science/article/pii/S0933365713001589)
- [Nature Article on Deep Learning for Skin Lesion Analysis](https://www.nature.com/articles/nature21056)
- [University of Bourgogne Document on Skin Lesion Segmentation](https://hal-univ-bourgogne.archives-ouvertes.fr/hal-01250955/document)
- [ISIC 2021 Workshop](https://workshop2021.isic-archive.com/)
- [ISIC 2020 Workshop](https://workshop2020.isic-archive.com/#paper)
