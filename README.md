# Melanoma Detection Assignment

## Objective
In this assignment, you will build a multiclass classification model using a custom convolutional neural network in TensorFlow

## Problem Statement
 To build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution that can evaluate images and alert dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.
## Dataset
The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images, with the exception of melanomas and moles, whose images are slightly dominant.
The data set contains the following diseases:
- Actinic keratosis
- Basal cell carcinoma
- Dermatofibroma
- Melanoma
- Nevus
- Pigmented benign keratosis
- Seborrheic keratosis
- Squamous cell carcinoma
- Vascular lesion


The data set contains the following diseases:
### Train Dataset
![Train-Data-Stats](https://github.com/ShashankPawas/Melanoma-Detection-Assignment/blob/main/Train-Data-Stats.png)

### Test Dataset
![Test-Data-Stats](https://github.com/ShashankPawas/Melanoma-Detection-Assignment/blob/main/Test-Data-Stats.png)

### Sample image from Dataset

![Image-Dataset](https://github.com/ShashankPawas/Melanoma-Detection-Assignment/blob/main/Image-Dataset.png)

## CNN Architecture Design
To classify skin cancer using skin lesions images. To achieve higher accuracy and results on the classification task, I have built custom CNN model.

- Rescalling Layer - To rescale an input in the [0, 255] range to be in the [0, 1] range.
- Convolutional Layer - Convolutional layers apply a convolution operation to the input, passing the result to the next layer. A convolution converts all the pixels in its receptive field into a single value. For example, if you would apply a convolution to an image, you will be decreasing the image size as well as bringing all the information in the field together into a single pixel. 
- Pooling Layer - Pooling layers are used to reduce the dimensions of the feature maps. Thus, it reduces the number of parameters to learn and the amount of computation performed in the network. The pooling layer summarises the features present in a region of the feature map generated by a convolution layer.
- Dropout Layer - The Dropout layer randomly sets input units to 0 with a frequency of rate at each step during training time, which helps prevent overfitting.
- Flatten Layer - Flattening is converting the data into a 1-dimensional array for inputting it to the next layer. We flatten the output of the convolutional layers to create a single long feature vector. And it is connected to the final classification model, which is called a fully-connected layer.
- Dense Layer - The dense layer is a neural network layer that is connected deeply, which means each neuron in the dense layer receives input from all neurons of its previous layer.
- Activation Function(ReLU) - The rectified linear activation function or ReLU for short is a piecewise linear function that will output the input directly if it is positive, otherwise, it will output zero.The rectified linear activation function overcomes the vanishing gradient problem, allowing models to learn faster and perform better.
- Activation Function(Softmax) - The softmax function is used as the activation function in the output layer of neural network models that predict a multinomial probability distribution. The main advantage of using Softmax is the output probabilities range. The range will 0 to 1, and the sum of all the probabilities will be equal to one.
- Batch Normalization - is a powerful technique that can improve the performance of your Tensorflow models. By reducing the internal covariate shift, batch normalization can help speed up convergence, improve generalization, and act as a form of regularization
- CallBack Used
	- ModelCheckPoint - is used in conjunction with training using model. fit() to save a model or weights (in a checkpoint file) at some interval, so the model or weights can be loaded later to continue the training from the state saved.
	- EarlyStopping -  is a form of regularization used to avoid overfitting when training a learner with an iterative method, such as gradient descent. Such methods update the learner so as to make it better fit the training data with each iteration.

### Model Architecture
![Final-Model-Arch](https://github.com/ShashankPawas/Melanoma-Detection-Assignment/blob/main/Final-Model-Arch.png)

### Model Evaluation
![Final-Model-Accuracy-Loss-Plot](https://github.com/ShashankPawas/Melanoma-Detection-Assignment/blob/main/Final-Model-Accuracy-Loss-Plot.png)

## Final Observation
- Based on the Plot and Above Accuracy & Loss rate, we have addressed the Underfitting and Overfitting problem.
- With Train Accuracy at 61.54 and Validation Accuracy at 61.47, seems we need to improve the accuracy.
- We have tried using DropOut, CallBack, Data Augumentation and Batch Normalization, which are some of the recommended steps to reduce to the OVerfitting / Underfitting.
- However, using the model to predict is debatable as the accuracy is still around 61%.

## References
Tensor Flow for Keras from https://www.tensorflow.org/api_docs/python/tf/keras/callbacks
https://www.tensorflow.org/api_docs/python/tf/keras/layers/BatchNormalization

TowardsDataScience from 
https://towardsdatascience.com/epoch-vs-iterations-vs-batch-size-4dfb9c7ce9c9

Interpreting Evalulation Plot from https://www.baeldung.com/cs/learning-curve-ml#:~:text=The%20training%20loss%20indicates%20how,the%20model%20fits%20new%20data.&text=Another%20common%20practice%20is%20to,those%20metrics%20for%20different%20models.

