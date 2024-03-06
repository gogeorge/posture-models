# Posture ML models

This repository offers one method of combining two models, in order to compare the cosine \
similiarities of the vectoral features in the dataset and a hybrid model that given a big \
enough of a dataset could be very effective in determining human movement and poses.

## CNN-LSTM model

The logic of combining a Convolutional Neural Network (CNN) and a Long Short Term Memory (LSTM) model \
comes from the idea of using the temporal abilities of an LSTM model and adding them on spatial abilities of a CNN. \
That is the CNN takes care of recognizing in an image edges, lengths and proportions of a body while the LSTM model can \
look into several images that are taken one after the other in order to determine differences in movement.

While the ``` cnn-lstm.ipynb ``` focuses on classifying three types of sitting postures, the concept that is explained \
in the aforementioned paragraph can be generalized into any sort of human poses that require a certain movement to be reached.


## Augmented Cosine Similarity Pose Metric (aCSPM)

This metric is based on the pre-existing cosine similarity equation. This equations compares the cosine angles of two vectors. \
When it comes to comparing two poses, this comparisson is not enough. Better explained in steps, this what the aCSPM does: 

1. Find the average coordinates (using mediapipe) of the body parts involved in all the classified poses
2. Compare them with the cosine rule and subtract these consequent coordinates from the coordinates of an unclassified pose
3. Scale these coordinate differneces into 0 to 1 results and use a fuse equation to combine these results with the predictions \
   of a model such as the CNN-LSTM.

This is a method that can be utlized when a model is underperforming in terms of accuracy. In this situation if the CNN-LSTM \
model is underperforming, the use of a model such as mediapipe pose detection can help improve the overal accuracy.


## Further reading

Both notebooks have adequate comments, nevertheless for more in-depth explanations and testing you can take a look in this thesis: 

http://essay.utwente.nl/96093/1/Valtas_BA_EEMCS.pdf



