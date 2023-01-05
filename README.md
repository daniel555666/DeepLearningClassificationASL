# Classification of American Sign Language: Assignment 3


Yehudit Brickner, 
Yaakov Khodorkovski, 
Daniel Zaken

![image5](https://user-images.githubusercontent.com/92545994/210875264-083a914b-ba22-4522-99b8-30722b34c8de.png)

Our project is classifying asl (American sign language) letters. The data set can be found here: https://www.kaggle.com/datasets/grassknoted/asl-alphabet .
In this dataset, there are 78,000 images in 26 classes: A-Z. (3000 images for each class)

The images are 200p x 200p = 40,000p.

Because that is a lot of features we decided to resize the images to 64 x 64.

We split the data into 70% training and 30% testing.

We took 80% of the testing data for validation.

For each class, we will have approximately 2100 images in the train set, 720 images in the validation set, and 180 images in the test set.


For the first part of the project, we created a simple multi-layer perceptron (MLP)  with 0,2,5 hidden layers with softmax for the classification.

For each of the above neural networks, we tried changing the respective parameters of the model: learning rate, epochs, with/without mini-batches, and the size of the layers, until we found a network that gave us good validation results.


![image6](https://user-images.githubusercontent.com/92545994/210875438-123a09b8-ce40-451c-928c-3bf710d6dc76.png)

![image4](https://user-images.githubusercontent.com/92545994/210875459-ceab00f3-f4fa-422e-aa38-8182b2b29148.png)





For the second part, we used a Convolution Neural Network to classify the data. Again we tried playing with the parameters, we tried adding different convolutional layers with different-sized kernels, and different padding to the kernel. We tried changing where we have max pooling layers. We played with the learning rate, number of epochs, and batch size.

This model has 3 convolutional layers with a kernel of size 5x5. The activation is ReLu.
The first convolutional layer has 8 kernels, and everyone after has double the amount of the one before. After each convolutional layer we have a max pooling layer of 2x2. After the last max pooling layer, we used a flatten layer to get a vector. We then did 3 fully connected layers.

We ran this model for 30 epochs with a batch size of 10 and a learning rate of 0.001, and then another 15 epochs with batch size of 10 and learning rate of 0.0001.


We decided to use a CNN for the second part of this assignment because it works well with images. The reason it works well with Images is that it takes into consideration each pixel and its surrounding to try and find bigger features like edges, corners, and more. Together it can find small features and slowly connect them together to bigger features.

## With this model we got 98.7% accuracy


![image1](https://user-images.githubusercontent.com/92545994/210875511-d7a1e5c0-a117-42c7-b9d0-b946bc04b595.png)


Confusion Matrix

![image2](https://user-images.githubusercontent.com/92545994/210875494-2d4f2d60-f294-433e-a34f-18a9e324efe1.png)




Accuracy score: (TP + TN) / (TP + TN + FP + FN).A high accuracy score means that the model is making a large proportion of correct predictions.

Precision score: TP / (TP + FP).A high precision score means that the model is not making many false positive predictions.

Recall score: TP / (TP + FN). A high recall score means that the model is not missing many positive cases.

F1 score: It is calculated as 2 * (precision * recall) / (precision + recall). A high F1 score indicates a balance between precision and recall.

Because our data is multiclassed we used weighted average to calculate these scores.

![image3](https://user-images.githubusercontent.com/92545994/210875332-b3a055ee-f207-4a8b-a3fe-64278d9bbeeb.png)
