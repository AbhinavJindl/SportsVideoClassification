# Overview
We are trying to build a classifier that distinguishes videos of 5 different activities. 

Videos can be viewed as a sequences of individual images; therefore, one can deal
with video classification as performing image classification L times, where L is
the number of frames in a video. However, this setting has a problem: it does
not capture the temporal nature of the video. That is why we use RNN-CNN for
video classification. Training RNN-CNN’s needs a lot of computational resources,
and it might sometimes be excessive, so in this project we will take a simpler
approach.

### Moving Averages over Predictions for Video Classification
In this approach, we train a CNN for image classification and turn it into a video
classifier using moving averages. If we rely on only one or a few frames of a
video for classifying it, we will observe a phenomenon called flickering, which is
assigning different labels to different frames of a video in the same class. However,
if we use an average of predictions of probabilities for multiple frames, we will get
a more reliable prediction for a video.

### Transfer Learning for Image Classification
When dealing with classification of relatively small image datasets, deep networks may not perform very well because of not having enough data to train
them. In such cases, one usually uses transfer learning, which uses deep
learning models that are trained on very large datasets such as ImageNet as
feature extractors. To perform empirical regularization, crop, randomly zoom, rotate, flip, contrast, and translate images in your training set for image augmentation.

### Video Classification Using Moving Averages
Apply at least L equally spaced frames of each video in the folder Sports Videos
to your model to obtain L vectors of probability predictions from
the softmax in your model. Calculate the average probability of
these probability vectors for each video. Select the class with the maximum probability in the vector probability for each video and
compare it to the actual label of the video.





