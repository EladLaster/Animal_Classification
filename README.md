# Animal Classification Project

## Overview
This project focuses on classifying images of mammals into five categories: dog, cat, horse, lion, and elephant.

The goal is to develop machine learning models capable of accurately identifying the mammal depicted in a given image.

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

## Mechine Learning Algorithms
Three classification models were trained on the data:

1) K-Nearest Neighbors (KNN)
2) AdaBoost
3) Decision Tree
4) Logistic Regression

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

Upon reviewing the results, while Logistic Regression performed the best on color (RGB) images with an accuracy of 59.92%, it's worth noting that on grayscale images, AdaBoost outperformed other algorithms with an accuracy of 48.73%.

This indicates that AdaBoost might be better at capturing relevant features or patterns in grayscale images, contributing to its higher accuracy in this particular scenario.

## 2) Are there types of mammals that are particularly similar and thus more difficult to classify?
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

Indeed, it's evident from our analysis that among the mammals in our dataset, the horse and elephant exhibit the highest degree of visual similarity.

This similarity can present a significant challenge for classification algorithms, as discerning between these two species based solely on visual features may prove more challenging compared to distinguishing between other pairs of mammals in the dataset.


## Conclusion
The animal classification project demonstrates the effectiveness of machine learning models in identifying mammal species from images.

Future work could involve refining preprocessing methods and exploring advanced classification algorithms to enhance model accuracy.
