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