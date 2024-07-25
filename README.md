# Animal Classification Project

## Overview

The main objective of this project is to perform image classification on a dataset consisting of images of five different mammal categories: dog, cat, horse, lion, and elephant.

The ultimate goal is to develop machine learning models that can accurately determine the specific mammal species depicted in a given image.

the primary aim of this project is to leverage machine learning techniques to build robust and accurate image classification models capable of identifying mammal species from images.

Through rigorous data preparation, model development, and evaluation, we aim to achieve a high level of performance and contribute to the field of computer vision and image recognition.

## Authors:

### Yair Turgeman
### Elad Laster

![2024-04-12 (1)](https://github.com/EladLaster/Animal_Classification/assets/118683420/ec5f73ed-0eb3-44cf-9eb3-3c2e076bc09e)


## Dataset
The dataset comprises 15,000 images of mammals, divided into two main folders: train and test.

Within each folder, there are subfolders for each mammal category.

*dataset source : https://www.kaggle.com/datasets/shiv28/animal-5-mammal*

## Data Preprocessing
* Train-Test Split & Shuffle & Resize:

  We split the dataset into training and testing sets to evaluate the performance of our models.
  Additionally, we shuffled the data to ensure that the order of the images does not influence model training.
  Furthermore, we resized all images to a consistent size (32x32 pixels) to standardize the input dimensions for our models.

* Show Few Pictures from the Data in RGB:

  We visually inspected a sample of images from the dataset in their original RGB (Red, Green, Blue) color format. This step helps us understand the visual characteristics of the images and the diversity    of the dataset.

* Show Data Distribution:

  We visualized the distribution of mammal categories within the dataset. This step provides insights into the class distribution, helping us understand potential biases or imbalances in the data.

* Classification on Images with the Models (on RGB):

  We trained classification models using the RGB images as input. This involved feeding the pixel data of the RGB images into the models and evaluating their performance in predicting the mammal   categories.

* Moving the Images to Grayscale:

  We converted the RGB images to grayscale, which involves representing each image using shades of gray rather than colors. This simplifies the data and reduces computational complexity while preserving     essential features for classification.

* Show Few Pictures from the Data in Grayscale:

  Similar to step 3, we visually inspected a sample of images from the dataset after converting them to grayscale. This step helps us understand how the grayscale conversion affects the appearance of the    images.

* Classification Again on Images with the Models (On Grayscale):

  We retrained the classification models using the grayscale images as input. This allowed us to assess how the performance of the models differs when using grayscale images compared to RGB images.

* Applying PCA (Dimensionality Reduction):

  We employed Principal Component Analysis (PCA) to reduce the dimensionality of our dataset. PCA is a technique used to transform the original feature space into a new set of uncorrelated variables,   
  known as principal components. By retaining as much information as possible while reducing the number of dimensions, PCA helps in simplifying the dataset and improving computational efficiency.

* Classification Again on Images with the Models (On RGB using PCA):

  We conducted classification once again, this time training the models using the reduced-dimensional data obtained from PCA, To see how this will affect the results.

## Mechine Learning Algorithms
Four classification models were trained on the data:

1) K-Nearest Neighbors (KNN)
2) Logistic Regression
3) Decision Tree
4) AdaBoost

# Our Main Questions

## 1) Does one of the algorithms we used worked better than the others?
The performance of each model was evaluated using a test set comprising 10% of the total data.

*Model Performance on RGB Images:*

* KNN: 45.06%
* Logistic Regression: 59.92%
* Decision Tree: 42.67%
* AdaBoost: 54.4%

*Model Performance on Grayscale Images:*

* KNN: 43.13%
* Logistic Regression: 46.87%
* Decision Tree: 40.93%
* AdaBoost: 48.73%

*Model Performance with PCA (on RGB Images):*

* KNN: 48.13%
* Logistic Regression: 58.70%
* Decision Tree: 42.40%
* AdaBoost: 52.06%

In our analysis, Logistic Regression emerged as the top performer for color (RGB) images, achieving an accuracy of 60.00% before PCA and 58.67% after PCA. However, when it came to grayscale images, AdaBoost surpassed other algorithms with an accuracy of 48.46%.

## 2) Are there types of mammals that are particularly similar and thus more difficult to classify?
We build a confusion matrix after every aldorithem we use to see the similarity.

*Most misclassifications between two mammals in Color (RGB) Images:*

* KNN: 167 wrong classifications - Horse & Elephant
* Logistic Regression: 97 wrong classifications - Horse & Elephant
* Decision Tree: 98 wrong classifications - Horse & Elephant
* AdaBoost: 76 wrong classifications - Horse & Elephant

*Most misclassifications between two mammals in Grayscale Images:*

* KNN: 152 wrong classifications - Horse & Elephant
* Logistic Regression: 95 wrong classifications - Horse & Elephant
* Decision Tree: 88 wrong classifications - Horse & Elephant
* AdaBoost: 77 wrong classifications - Horse & Elephant

*Most misclassifications between two mammals after using CPA(on RGB Images):*

* KNN: 132 wrong classifications - Horse & Elephant
* Logistic Regression: 87 wrong classifications - Horse & Elephant
* Decision Tree: 102 wrong classifications - Horse & Elephant
* AdaBoost: 108 wrong classifications - Horse & Elephant

Indeed, it's evident from our analysis that among the mammals in our dataset, the horse and elephant exhibit the highest degree of visual similarity.

This similarity can present a significant challenge for classification algorithms, as discerning between these two species based solely on visual features may prove more challenging compared to distinguishing between other pairs of mammals in the dataset.

## 3) Did using PCA on the images or converting them to grayscale lead to better results compared to classification on the original images?

When analyzing the results, it's evident that the performance was poorest on grayscale images. This suggests that color is a crucial factor in image classification. It's reasonable to assume that in images with multiple colors, color serves as a vital aid in classification, thus resulting in improved performance.

After implementing PCA for dimensionality reduction, we observed that the results were similar to those obtained before PCA. This is likely because, despite reducing the details and focusing primarily on the fundamental basis of the data, the quality of classification was not significantly compromised. By prioritizing the most informative features and discarding less relevant ones, PCA effectively maintains the integrity of the classification process while streamlining the computational complexity.

Choosing to utilize the PCA method is indeed a significant step. Based on the results we've obtained, it seems that employing PCA has led to simultaneously reducing runtime - with results comparable to those prior to PCA. the use of this method appears beneficial in handling large datasets and enhancing the accessibility and efficiency of the models and their runtime.
### Therefore, we recommend incorporating PCA as part of the data analysis and classification process.


## Conclusion

In summary, our animal classification project employed machine learning techniques to classify mammal species from images.

We found that while Logistic Regression performed best on RGB images before and after PCA , AdaBoost excelled on grayscale images.

Our analysis revealed the challenge of distinguishing visually similar species, notably horses and elephants.

Looking ahead, further exploration of advanced algorithms and feature engineering could boost accuracy and make our approach more practical for real-world applications.
