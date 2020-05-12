# Style Transfer
Style transfer is a technique in which two images are take an object image and a style image, the style image is usually a painting which has properties like colour, saturation, specific strides etc.. the object image is which has the object to which we need to apply this style. The neural network learns from the style image the properties and applies it to the object image to give an output image which has the style of the style image but the object that we provided.

One of the most significate application is Google's Deep dream project.

[Tensorflow documentation of deep dream](https://www.tensorflow.org/tutorials/generative/deepdream)

[Github repo](https://github.com/google/deepdream)

We would be using VGG16 to feed in the object image and style image so that It would recognise the style on the first image and apply the same on the object image to create our required image.

## Content Loss

Content loss makes sure that the content in the content image is presen in the generated image. To calculate content loss we use mean squared error between the genrated iamge and content image.

## Gram Matrix
What we need to do is actually find the correlation between two layers of a neural network in order to do this first we need to vectorise the image we can do this simply by flatterning the 3d image to a 2d vector, then we take the flattened image and its transpose and multiply them together to get the gram matrix.

## Style Loss
To calculate the style loss we calculate the mean squared distance between the target image and the style image's gram matrices. For all layers taken as a list we will multiply this weight by a style weight and then add all of them up.

## Total Loss
This is the sum of Style Loss and Content Loss. We can use this loss with back propogation and optimisation to reduce the loss.

## Loss Weights
Since we are using two different losses here the higher one might interfear with the backpogation step so what we need to do is multipy both these losses with two weights lets say alpha for content and beta for style this would make sure that the losses are taken equally into account so if we take the ratio between these two weights are actually changed so that it can effect the output image.

Click [here](https://github.com/abhijitramesh/leonardo/blob/master/Style_Transfer_Exercise.ipynb) to see the implementation of [this](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf) paper for Style Transfer