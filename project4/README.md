# Individual Project 4:
# Image Generation with conditional GAN

#### Due Date
* Tuesday Nov 3, 2023 (23:59)

#### Total Points 
* 100 (One Hundred)

## Goal
In this assignment you will implement a Conditional Generative Adversarial Networks (cGAN) with [MNIST data set](http://yann.lecun.com/exdb/mnist/). This project will be completed in Python 3 using [Keras](https://keras.io/). 


## Project Guidelines

#### Data set

MNIST is a dataset composed of handwrite numbers and their labels. Each MNIST image is a 28\*28 grey-scale image, which is labeled with an integer value from 0 and 9, corresponding to the actual value in the image. MNIST is provided in Keras as 28\*28 matrices containing numbers ranging from 0 to 255. There are 60000 images and labels in the training data set and 10000 images and labels in the test data set. Since this project is an unsupervised learning project, you can only use the 60000 images for your training. 

#### Installing Software and Dependencies 

* [Install Anaconda](https://docs.anaconda.com/anaconda/install/)
* [Create virtual environment](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)
* Install packages (e.g. pip install keras)

#### Building and Compiling Generator and Discriminator

You are allowed to use any deep learning package, such as Tensorflow, Pytorch, etc. In Keras, Models are instantiations of the class Sequential. You can try different layers, such as “Conv2D”, different activation functions, such as “tanh”, “leakyRelu”. To compile the model, different optimizer, such as stochastic gradient descent and different loss function are also allowed. 



#### Training cGAN

You have the option of changing how many epochs to train your model for and how large your batch size is. 



#### Plotting

Please generate some sample images for each digit (we provide and example as below). Please also plot the training loss for both generator and discriminator (an example as below).

Examples:
<img src="https://github.com/yingxue-zhang/INFO536/blob/main/project4/results.png" width="80%">

<img src="https://github.com/yingxue-zhang/INFO536/blob/main/project4/loss.png" width="80%">


## Deliverables

Please compress all the below files into a zipped file and submit the zip file (firstName_lastName_cGAN.zip) to Canvas. 

#### PDF Report
* Set of Experiments Performed: Include a section describing the set of experiments that you performed, what structures you experimented with (i.e., number of layers, number of neurons in each layer), what hyperparameters you varied (e.g., number of epochs of training, batch size and any other parameter values, weight initialization schema, activation function), what kind of loss function you used and what kind of optimizer you used. 
* Special skills: Include the skills which can improve the generation quality. Here are some [tips](https://github.com/soumith/ganhacks) may help.   
* Visualization: Include the final generated images which formatted as the example as above and a loss plot of the generator and discriminator during your training (as above). 

#### Python code
* Include model creation, model training, plotting code.

#### Generator Model
* Turn in your best generator saved as “generator.json” and the weights of your generator saved as “generator.h5”.


## Grading

#### Report (70%)

* Set of experiments performed: 30 points
* Special skills: 20 points
* Visualization: 20 points

#### Code (20%) 

You can get full credits if the scripts can run successfully (i.e., TA will test your code with a small data set to see if images can be generated), otherwise you may loss some points based on your error. Similar to project 2, you should submit a evaluation.py file.

#### Model (10%)

You can get full credits if all the generated images can be recognized, otherwise you may loss some points. Also, the code you submitted should be able to generate all 10 different digits.
