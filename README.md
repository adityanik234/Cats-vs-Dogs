# Cats-vs-Dogs
A binary Image Classifier for Cats-vs-Dogs classification using Convolutional Neural networks with Data Augmentation in Python.

I ran two experiments, in the first, the model was trained on the dataset without data augmentation while in the second, it was trained with it.
The model uses four 2D convolutional layers each with 32, 64, 128 and 128 convolutions respectively along with 2D Maxpooling which was trained for 100 epochs.

In the fist experiment the Training accuracy is nearly 100% while the Validation accuracy is just over 70% which clearly shows that the model is overfitting the data which means that if we were to show the model images of cats or dogs it hasn't trained on before it wouldn't be able to correctly classify them. This poses a major issue when used in real world applications like for example if we used a model to predict if a person has cancer or not, with an overfitting model it might happen that a perfectly normal person is classified as having cancer and will be given treatment accordingly when its unnecessary and vice versa. Hence we have to eliminate overfitting at all costs!

So, how do we eliminate or at least reduce overfitting?

One way to do it is to augment the images a bit. For this experiment we have used images of cats and dogs and come to think of it most of the physical feature of cats or dogs are quite similar -- the ears are at the top, then the eyes, then the mouth etc. Things like the distance between the eyes and ears will always be quite similar too. These features are similar for images of cats and for images of dogs but they will differ if you compare images of cats with dogs.
So basically if we tweak the images a little like rotate the image, squash it, etc we are augmenting the images i.e. we are using Data augmentation. This helps the model focus on the distinguishing features of cats and dogs, and helps in greatly improving validation accuracy as shown in the plots obtained. This shows that Data augmentation has a regularizing effect. Data augmentation in this experiment was implemented using the ImageDataGenerator API in Tensorflow 2.0.

Lastly, apart from behaving as a regularizer it also helps when you have a small dataset to train your model on as every time data augmentation is applied to an image, the newly augmented image is treated as a new image.
