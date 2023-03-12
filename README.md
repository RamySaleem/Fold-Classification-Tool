# Fold-Classification-Tool

## Automatic classification of fold geometries from outcrop images using deep learning


## Abstract
Machine learning is being presented as a new solution for a wide range of geoscience problems. Primarily machine learning has been used for 3D seismic data interpretation, processing, seismic facies analysis and well-log data correlation. The rapid development in technology with open-source artificial intelligence libraries and the accessibility of affordable computer graphics processing units (GPU) makes the application of machine learning in geosciences increasingly tractable. However, the application of artificial intelligence in structural interpretation workflows of subsurface datasets is still ambiguous. This study aims to use machine learning techniques to classify images of folds and fold-thrust structures. Here we show that convolutional neural networks (CNNs) as supervised deep learning techniques provide excellent algorithms to discriminate between geological image datasets. Outcrop images and modelled datasets have been used to train and test ML models. This dataset comprises three classes (Box, Chevron and Rounded) of folds types. These image datasets are used to investigate a wide range of shallow, deep and transfer machine learning models. One traditional machine learning and five convolutional neural network models (Convolution 2D layer with Residual block model (ResNet with 9, 34, 50, 101 and 152 layers)). Validation and testing datasets form a critical part of testing the model’s performance accuracy. The ResNet-50 model records the highest performance accuracy score of the machine learning models tested. Our CNN image classification model analysis provides a framework for applying machine learning to increase structural interpretation efficiency and shows that CNN classification models can be applied effectively to geoscience problems. The study provides a starting point to apply deep learning approaches to sub-surface structural interpretation workflows.

## Introduction
Folds are wavelike structures that occur during permanent deformation (Ramsay and Huber 1987). They are formed when beds and layers are transformed into curved, bent, and crumpled shapes (Ramsay and Huber 1987). They are perhaps the most common tectonic structure developed in deformed rocks. Folds are an expression of ductile deformation which produces gradual and more continuous changes in a rock layer, both in attitude and internally (Ramsay and Huber 1987). The folds as structures are categorised as Box, Chevron and Rounded based on their geometrical hinge shape (the point with maximum curvature). The geometric analysis of folds forms the basis for the kinematic and dynamic analyses. In geometrical analysis, the structures and their homogeneity with respect to different domains were investigated. Geometric analysis is essential not only in order to understand how various types of folds form but also to provide a platform to understand the regional structure, quantify deformation and consequently explore tectonic processes. 


## Datasets
### Images dataset
In this study, the Folds dataset was created by two techniques first, gathering publicly available open-source images and second, building synthetic datasets, which total 4281-fold images, shared on an open-source folder. We manually labelled the image dataset, which we classified using the three classes Chevron, Box and Rounded folds. This data set was modelled using the traditional ML and deep learning methods with a series of models prepared in Python programming language and shared on an open-source GitHub repository. In this work, we used the following datasets:
1)	Real Image Dataset: We used an open-source database containing outcrop images of Chevron, Box and Rounded folds interpreted in this study. 
2)	Synthetic Dataset: We used synthetic image datasets of Chevron, Box and Rounded folds. The synthetic images are generated by modelling using MOVE suite structural software based on Ramsay’s fold geometry classification (1987).
The image datasets used here consist of outcrop data collected from online open-source image libraries (25%) and modelled image data (75%). The outcrop images are 1366, and the synthetic images are 2915 (Table 1). The total number of images used in this study is 4281, divided across three-fold classes (Box, Rounded and Chevron). Box folds are 1346, Chevron folds are 1439, and Rounded folds are 1496 images where all three classes are balanced throughout the dataset. Since the mathematical models cannot infer textual labels, they are encoded into numerical values. The order of labels is not mandatory, as the label is a dependent variable. The details of the datasets are summarised in the following table.

![](https://i.imgur.com/Rb9NzRH.png)

## Data Folder
Having an open-source, free dataset is essential for the geoscience community because it allows researchers and practitioners to assess the performance of different models and algorithms. All data from this study are available in the data folder, https://drive.google.com/drive/folders/1pXuUA6LxZYX6IP2IgbeNEo1346AzyxBj?usp=sharing.  All the data are open-source. 
If a dataset is open-source, then it is easy to compare the performance of different models or algorithms on that dataset. Open-source, free dataset allows researchers to develop and test their models on a more diverse set of data, which can lead to more robust and generalizable models. This can be particularly important in geoscience, where real-world data is often complex and varied, and models must perform well under various conditions.
A free dataset can also help identify areas where existing models or algorithms are deficient, or new ones are needed. By testing models on various datasets, researchers can identify common problems or areas where models are consistently struggling, which can then be used to inform future research directions. Overall, a free dataset is essential for the geoscience community because it allows for more robust and generalizable models, helps identify areas for improvement, and avoids introducing bias in model development and evaluation.



# Workflow
## CNN
CNN is a type of neural network commonly used in deep learning for image classification, object detection, and segmentation tasks. CNNs are designed to automatically learn spatial hierarchies of features from input images by performing convolution operations and pooling operations. Convolution layers apply a set of learnable filters to the input image to extract features at different spatial scales, while pooling layers downsample the feature maps to reduce their dimensionality and introduce some degree of translation invariance. CNNs typically end with one or more fully connected layers that map the extracted features to the output classes. CNNs have achieved state-of-the-art performance on a variety of image-related tasks and are widely used in computer vision applications (Lecun et al. 1998).


## Transfer learning
Transfer learning is a common technique in computer vision because it allows scientists to utilise existing models quickly and accurately (Rawat and Wang 2017) instead of starting the learning process from scratch. It allows researchers to leverage previous learnings and avoid training from scratch. Transfer learning is also the method of using the knowledge gained while resolving some problems and applying it to different but related problems. Transfer learning includes training the deep neural network for a precise task using a large-scale dataset such as ResNet. In the transfer learning method, the CNN is initially trained and gains base knowledge, where the model uses this knowledge to extract new features successfully. Generally, the dataset involved in the new problem is small compared to training the CNN from scratch. In order to get valuable results from the neural network by feature extraction, the dataset must have a couple of thousands of data points per class (Yu and Ma 2021). The most critical factor for successfully extracting the significant feature in the training process is data availability and accessibility.

![](https://i.imgur.com/XD4Lj16.png)

# Results
## Deep Learning Results

In this study, 4281 Fold-dataset images were modelled with five deep-learning models where the ResNet-50 recorded the highest accuracy. We used the Adam optimiser, which uses momentum and adaptive learning rates for faster training. Instead of a fixed learning rate, we used a one-cycle scheduled learning rate (Smith and Topin 2018), which changed the learning rate after every training batch. Figure 11 shows the learning rate graph of the Resnet-50 model is given. When the graphic was analysed, the learning rate for the Resnet-50 model was taken as 0.0007, and the training process was carried out. Choose an appropriate batch size (400), epochs (80) and learning rates to avoid overfitting during the training phase. In order to check that there is no overfitting in the trained model, it was verified with the validation dataset during the training phase and tested using different data at the end of the training.

![](https://i.imgur.com/4jYcktj.png)
Fold dataset distribution used in this study after labelling (Box, Chevron and Rounded) and splitting into training, validation and testing sets.

![](https://i.imgur.com/zxOEW7r.png)
Examples of the classification performed by the pre-trained ResNet-50 model. The model confidently assigned the image to the correct class. The red box shows an example of the model failing to assign the class correctly.



# Discussion
## Using the Fold Classification Modle
The results for 3913 training images of folding styles with three classes indicate an overall accuracy of 70% on the validation and 75% on the testing sets. Using these ML models can guide geologists in interpreting fold structures. Our workflow can quickly classify fold types for thousands of outcrop images using current standard consumer computer hardware (Section 4.1.1). The Box and Chevron labels are the most challenging to predict because they are less common in this dataset (Figure 15). A lack of training data further reduces the model prediction.
This workflow will be very useful for basin-scale studies of specific structure styles (e.g., fold-thrust structures) or for applications where a geologist could conduct an initial screening to highlight fold types within the area of interest. This technique is of particular value in cases where interpreting fold styles in individual outcrop images is not feasible due to the volume of images to process or the images are not available for an in-person examination. An example of this would be images from virtual outcrop models for educational purposes, such as examining entire databases of the eRocK virtual geology project led by Adam Cawood and Clare Bond at The University of Aberdeen or the Virtual Outcrop Geology Group between NORCE Norwegian Research Centre in Bergen, Norway, and the University of Aberdeen, UK.

However, the accuracy produced by this study cannot replace outcrop image interpretations performed by trained geoscientists, nor is it meant to - this study attempts to incorporate the full range of structural styles in three classes. The three labels of folds classes are broad and provide no insight into tectonics, sedimentary structures, mechanical stratigraphy, structural styles or complexity (such as in fold-thrust structures). We attempted to examine some of this detail using a multi-labelling scheme in more complex structures, with unsatisfactory results (GitHub repository). These more complex structures could be labelled and predicted using ML methods. Nevertheless, this research result indicates that increasing the number of classes by increasing the structural complexity without accompanying increases in training data is not advised with this dataset. Investigating these more complex structures and their accuracy will be applied in subsequent studies. Geologic class labels with complex structures (e.g., fold-thrust structures) will need a specific and consistent workflow to be successful.
Furthermore, while we labelled each class as reliably and accurately as possible, errors may exist in our labels since the outcrop images contain several labels together in multi-folding, or our label selection was biased by previous training, experience, and uncertainty (Bond et al. 2007). Because label selection is inherently qualitative, we did not incorporate any uncertainty metric into our labelling scheme. Each label was considered the absolute correct answer in this study, and if the label is incorrect, it will affect the accuracy of the resulting inference. Future work could develop a method for assigning uncertainty to geologic data and propagating that error into the modelling workflow, including uncertainty distance from the source of information in zones and levels. Finally, we hope that this study can serve as a baseline for future work to improve ML model applications and selection methodologies.

## Conclusion

This study used deep learning models to detect fold classes using outcrop images. Two types of datasets were used in the study. One is a real image of folds outcrop data, and the other is a modelled synthetic folds dataset. The fold images show three classes: Box, Chevron and Rounded. A collaboration of geoscience professionals is required to check if the model extracts sufficient features for each fold class to predict fold types accurately. This work focused on the working principle of training versus transfer learning and explored using the pretrained Resnet model on folds images. The study shows a fast, robust and effective method of classifying fold structures, which can help in the fast interpretation of fold types.
This study compares the performance of multiple traditional ML algorithms with the accuracy produced by deep learning techniques, specifically convolution neural networks (CNNs). It has been noted that Random Forest produced the best accuracy among the traditional ML techniques. However, the deep learning technique (ResNet-50) produced better accuracy than Random Forest on validation and testing datasets. Additionally, colour does seem to be a critical feature for the accurate classification of fold images, and training on coloured images can give a boost in accuracy when fine tun on structure images.
This research demonstrates the possibility of classifying fold structures derived from actual and synthetic images using fully open-source Python packages. We believe this study could be used as an initial classification, which can help geoscience professionals interpret fold structures by quickly classifying the fold types. It provides not only a fast but also an automatic fold classification method, which helps a better understanding of fold structure. The research presented here will also guide other geoscientists in selecting suitable ML models. This workflow can be scaled from thousands of outcrop images to millions of virtual outcrop models worldwide.

![](https://i.imgur.com/bttX7Dl.gif)

Acknowledgements 
=================
The work contained in this paper contains work conducted during a PhD study undertaken as part of the Natural Environment Research Council (NERC) Centre for Doctoral Training (CDT) in Oil & Gas funded 50% through its National Productivity Investment Fund grant number NE/R01051X/1 and 50% by the University of Aberdeen through its PhD Scholarship Scheme. The support of both organisations is gratefully acknowledged. The work is reliant on Open-Source Python Libraries, particularly Pytorch, Numpy and Matplotlib, and contributors to these are thanked, along with Jovian and GitHub, for open-access hosting of the Python scripts for the study.

![University of Aberdeen](https://pbs.twimg.com/profile_images/1572172791801061377/UPSWmPyN_400x400.jpg)

![NERC-CDT](https://nerc-cdt-oil-and-gas.ac.uk/wp-content/uploads/news/2015-news-NERC-funding.jpg)

![NERC](https://auracdt.hull.ac.uk/wp-content/uploads/2019/11/UKRI_NER_Council-Logo_Horiz-RGB.png)

![CDT](https://i.imgur.com/QDOhcN3.png)






