# Behavioral Cloning Implementation in Keras
**Project Overview:** With in this projet the objective to drive a car aunomostly around a track using a deep neural network. The netural network is trained to predict the suitable steering angles based on the images that are available from the three cameras in fornt of the car. The training data set is collected by driving the car manually around the track and recording the images from the cameras as the input feature and the steering angles as the labels. The outline of the project is:

* Data collection and Visualization
* Data distribution correction
* Data Augmentation and adding the data from right and left cameras
* Normalization and Pre-processing
* Deep Netural Network Artchitercture
* Neural Network Training

# 1. Data Collection and Visualization
Probably the most important part of this project which is playing a major role in the performance of the trained model is the data collection. In fact the trained deep neural network will learn and clone the driving pattern of the driver from the collected data. Therefore, if the quality of the data is not good the network will not be able to navigate the car sucessfully around the track.

* Summary of the collected data
1. Data available from udacity
2. Three rounds driving in the center of the roud in forward direction
3. Three rounds driving in the center of the roud in oposite direction
4. One round recovery from the off-center condition in forward direction
5. One round recovery from the off-center condition in oposite direction
6. One round just passing through the turns in forward direction
7. One round just passing through the turns in oposite direction

I combined all these collected data from the data provided by udacity, and in total it was about 1.5GB of data. In my experince collecting more data was the key to solve the problem. The more data I collected the model was generalzing better.

Figures below shows a few examples of the collected data.

# 2. Data distribution correction
I deep learning applicatins having a good understanding of the statistics of the training data can be useful to train a efficient model. Figure below shows the histogram of the distribution of the **steering angles**

As it is clear the steering angles are concentrated to value **zero** because most parts of the track are straigh. Using this data set to train the model will result to a model which is highly biased to **zero** steering angles, in other words the model will be more accurate in predicting **zero** steering angles, and it will be facing difficulties while predicting the steering angles while entering the turns. In order to overcome this draw back I excluded some of the data points associated with the zero steering angle. I excluded half of the data points with zero steering angle randomly. The distribution of the new data set is as shown in figure below.

Using this data distribution the model will be less biased towards **zero steering angles**


