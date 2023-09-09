# Face Recognition with Histogram-of-Oriented-Gradients

## Description:

[**Histogram of Oriented Gradients**](https://scikit-image.org/docs/stable/auto_examples/features_detection/plot_hog.html) (`HOG`) algorithm is used to extract features from human faces which are fed as _positive_ examples into a classifier for face detection.

**Keywords: `Image Processing,` `Data Wrangling,` `Machine Learning,` `SVC Classifier.`**

<br>
<p align="center">
<img src="./Static/HOG TRANSFORMATION.png" alt="ugraph" width="500" height="300" />
<br>
<i>Image processed with HOG</i>
</p>
<br>

## Requirements:

- Python 3.9.7
- numpy
- scikit-image
- matplotlib
- scikit-learn

## The Dataset:

To train the classifier we need two types of examples, 1) Positive examples which are images of faces where we going to extract features that the classfier will _"learn"_, and 2) Negative examples which are non-face images used as the _"false"_ class. Both type of images will form our dataset.

For the positive images the [`Labeled Faces in the Wild`](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_lfw_people.html) dataset included in Scikit-Learn is used (**10,000 images**) and to create our negative images several categories of images from [Scikit-Image](https://scikit-image.org/docs/stable/auto_examples/data/plot_general.html) are used (**3,000 images**).

<br>
<p align="center">
<img src="./Static/DATASET FACES-IN-THE-WILD.png" alt="ugraph" width="500" height="300" />
<br>
<i>Sample of positive images from Faces in the Wild Dataset</i>
</p>
<br>

A total of `13,000` images are used to create our dataset.

**NB: Due to `GitHub` limitation on files larger that _100 MB_ the datasets have to be removed. In the accompanied notebook the dataset used for the project can be reproduced.**

## Face Detection Classifier:

The model selected for the face detection classifier was a support vector machine due to this type of models have proved excelent performance among other type of machine learning classification algorithms.

The _train_ dataset with the 13,000 images previously processed with the `HOG` algorithm is fed into the **SVM** along with the labels for _positive_ and _negatve_ examples.

For the lables, we selected two classes:

- `class 1,` which is positive for human face.
- `class 0,` which is negative for human face.

## Testing the Complete Pipeline:

To test our classifier two images are used, one _positive_ image and one _negative_ image.  
To do the test we need to run the complete pipeline, namely we need:

- Resize the image
- Compute HOG for the image
- Feed image into clssifier to do the prediction

<br>
<p align="center">
<img src="./Static/SVM FACE DETECTION.png" alt="ugraph" width="500" height="300" />
<br>
<i>Test Images</i>
</p>
<br>
