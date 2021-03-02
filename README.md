# [Project 3 - Computer Vision 2020/2021](https://github.com/Gideon996/Computer-Vision-2020/blob/main/project_assignments.pdf)

This project requires the implementation of an image classifier based on convolutional neural networks. The [provided dataset](https://github.com/Gideon996/Computer-Vision-2020/tree/main/ImageSet) contains 15 categories and is already divided in training set and test set.

## Required Point:
- train a shallow network from scratch according to the following specifications:
  - use the network layout shown in Table 1:
  - since the input image is 64×64 you will need to resize the images in order to feed them to the network; follow the simple approach of rescaling the whole image independently along x and y to get the proper size. Other approaches exist, see below about the optional improvement of data augmentation;
  - split the provided training set in 85% for actual training set and 15% to be used as validation set;
  - employ the stochastic gradient descent with momentum optimization algorithm, using the default parameters of the library you use, except for those specified in the following;
  - use minibatches of size 32 and initial weights drawn from a Gaussian distribution with a mean of 0 and a standard deviation of 0.01; set the initial bias values to 0;
  - by using a proper value for the learning rate, you should be able to obtain an overall test accuracy of around 30% 1;
  - report and discuss the plots of loss and accuracy during training, for both the training set and the validation set;
  - comment on the criterion you choose for stopping the training;
  - report the confusion matrix and the overall accuracy, both computed on the test set.
- Improve the previous result, according to the following suggestions (not all the following will necessarily result in an increase of accuracy, but you should be able to obtain a test accuracy of about 60% by employing some of them):
  - data augmentation: given the small training set, data augmentation is likely to improve the performance. For the problem at hand, left-to-right reflections are a reasonable augmentation technique. By augmenting the train data using left-to-right reflections you should get an accuracy of about 40%;
  - batch normalization [Ioffe and Szegedy, 2015]: add batch normalization layers before the reLU layers;
  - change the size and/or the number of the convolutional filters, for instance try increasing their support as we move from input to output: 3×3, 5×5, 7×7;
  - play with the optimization parameters (learning rate, weights regularization, minibatch size . . . ); you can also switch to the adam optimizer;
  - dropout: add some dropout layer to improve regularization;
  - employ an ensemble of networks (five to ten), trained independently. Use the arithmetic average of the outputs to assign the class, as in [Szegedy et al., 2015].
Comment on any significant change you notice after the application of the
previous modifications.
- Use transfer learning based on a pre-trained network, for instance AlexNet [Krizhevsky et al., 2012], in the following two manners (in both of the cases you should get a test accuracy above 85%):
  - freeze the weights of all the layers but the last fully connected layer and fine-tune the weights of the last layer based on the same train and validation sets employed before; 
  - employ the pre-trained network as a feature extractor, accessing the activation of an intermediate layer (for instance the last convolutional layer) and train a multiclass linear SVM. For implementing the multiclass SVM use any of the approaches seen in the lectures, for instance DAG.
- OPTIONALLY: in tasks 2 and 3, you could improve data augmentation, adding to the left-right reflection a random cropping of a sufficiently large region, followed by small rotations and rescaling (an example of crop and rescaling is shown in Fig. 3);
- OPTIONALLY: in task 2, you could add more convolutional and/or fullyconnected layers;
- OPTIONALLY: in task 3, you could employ nonlinear SVMs;
- OPTIONALLY: in task 3, you could implement the multiclass SVM using the Error Correcting Output Code approach


# Developers
- [Pinna Giovanni](https://www.giovannipinna.net)
- [Tumino Adriano](https://github.com/Gideon996)
