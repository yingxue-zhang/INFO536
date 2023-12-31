
# Individual Project 3:
# Image Generation with GAN

#### Due Date
* Tuesday Oct 17, 2023 (23:59)

#### Total Points 
* 100 (One Hundred)

## Goal
In this assignment you will implement a Generative Adversarial Networks (GAN) with [MNIST data set](http://yann.lecun.com/exdb/mnist/). This project will be completed in Python 3 using [Keras](https://keras.io/). 

<img src="https://github.com/yanhuata/DS504CS586-S20/blob/master/project3/pic/goal.png" width="80%">


## Project Guidelines

#### Data set

MNIST is a dataset composed of handwrite numbers and their labels. Each MNIST image is a 28\*28 grey-scale image, which is labeled with an integer value from 0 and 9, corresponding to the actual value in the image. MNIST is provided in Keras as 28\*28 matrices containing numbers ranging from 0 to 255. There are 60000 images and labels in the training data set and 10000 images and labels in the test data set. Since this project is an unsupervised learning project, you can only use the 60000 images for your training. 

#### Installing Software and Dependencies 

* [Install Anaconda](https://docs.anaconda.com/anaconda/install/)
* [Create virtual environment](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)
* Install packages (e.g. pip install keras)

#### Building and Compiling Generator and Discriminator

You are allowed to use any deep learning package, such as Tensorflow, Pytorch, etc. In Keras, Models are instantiations of the class Sequential. You can try different layers, such as “Conv2D”, different activation functions, such as “tanh”, “leakyRelu”. To compile the model, different optimizer, such as stochastic gradient descent and different loss function are also allowed. The following is the sample code of how to build and compile the models.


```python
# Optimizer
adam = Adam(lr=0.0002, beta_1=0.5)

# To create generator, you can define a function which returns a Sequential object.
g = create_generator()(self-defined function)


# To create discriminator, you can define a function which returns a Sequential object.
d = create_discriminator()(self-defined function)

# GAN
d.trainable = False
inputs = Input(shape=(z_dim, ))
hidden = g(inputs)
output = d(hidden)
gan = Model(inputs, output)
gan.compile(loss='binary_crossentropy', optimizer=adam, metrics=['accuracy'])
```

#### Training GAN

You have the option of changing how many epochs to train your model for and how large your batch size is. The following is the sample code of how to train GAN. You can add seld-defined parameters such as #epoch, learning rate scheduler to the train function.



```python
# Training
def train():
    for _ in range(batchCount):  
	
        # Create a batch by drawing random index numbers from the training set
       
        # Create noise vectors for the generator
        
        
        # Generate the images from the noise

        # Create labels

        # Train discriminator on generated images

        # Train generator

```

#### Saving Generator

Please use the following code to save the model and weights of your generator.



```python
# serialize model to JSON
model_json = g.to_json()
with open("generator.json", "w") as json_file:
    json_file.write(model_json)
# serialize weights to HDF5
g.save_weights("generator.h5")
```

#### Plotting

Please use the following code to plot the generated images. As for the loss plot of your generator and discriminator during the training, you can plot with your own style. 


```python
# Generate images
np.random.seed(504)
h = w = 28
num_gen = 25

z = np.random.normal(size=[num_gen, z_dim])
generated_images = g.predict(z)

# plot of generation
n = np.sqrt(num_gen).astype(np.int32)
I_generated = np.empty((h*n, w*n))
for i in range(n):
    for j in range(n):
        I_generated[i*h:(i+1)*h, j*w:(j+1)*w] = generated_images[i*n+j, :].reshape(28, 28)

plt.figure(figsize=(4, 4))
plt.axis("off")
plt.imshow(I_generated, cmap='gray')
plt.show()
```

## Deliverables

Please compress all the below files into a zipped file and submit the zip file (firstName_lastName_GAN.zip) to Canvas. 

#### PDF Report
* Set of Experiments Performed: Include a section describing the set of experiments that you performed, what structures you experimented with (i.e., number of layers, number of neurons in each layer), what hyperparameters you varied (e.g., number of epochs of training, batch size and any other parameter values, weight initialization schema, activation function), what kind of loss function you used and what kind of optimizer you used. 
* Special skills: Include the skills which can improve the generation quality. Here are some [tips](https://github.com/soumith/ganhacks) may help.   
* Visualization: Include 25 (5\*5) final generated images which formatted as the example in Goal and a loss plot of the generator and discriminator during your training. For generated images, you need to generated at least one image for each digit. 

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

