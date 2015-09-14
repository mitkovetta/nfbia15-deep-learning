# Model description

- Input 65x65
- Convolution 1x6x6x48
- Hyperbolic tangent nonlinearity
- Max pooling 2x2
- Convolution 48x5x5x48
- Hyperbolic tangent nonlinearity
- Max pooling 2x2
- Convolution 48x4x4x48
- Hyperbolic tangent nonlinearity
- Max pooling 2x2
- Convolution 48x2x2x48
- Hyperbolic tangent nonlinearity
- Max pooling 2x2
- Fully connected (48x2x2)x100
- Hyperbolic tangent nonlinearity
- Fully connected 100x2
- Softmax
 
This model is based on an implementation by Dan Ciresan (http://people.idsia.ch/~ciresan/).

For the fully convolutional model the two fully-connected layers are replaced with:
- ...
- Convolutional 48x2x2x100
- Hyperbolic tangent nonlinearity
- Convolutional 100x1x1x2
- Hyperbolic tangent nonlinearity
- Softmax

# Learning curves
![Learning curves](/examples/drive/images/learning_curves.png)

# Filter appearance
The filters below are from the model after 200000 iterations.

## Filters in first convolutional layer
![Filters in first convolutional layer](/examples/drive/images/conv1.png)

## Filters in second convolutional layer
![Filters in second convolutional layer](/examples/drive/images/conv2.png)

## Filters in third convolutional layer
![Filters in third convolutional layer](/examples/drive/images/conv3.png)

## Filters in fourth convolutional layer
![Filters in fourth convolutional layer](/examples/drive/images/conv4.png)

# Example segmentation

## Input
![Input](/examples/drive/images/example_test_input.png)

## Segmentation

This result is the average of 4 outputs (test-time augmentation): original image and flipped image in horizontal, vertical and both directions.

![Segmentation](/examples/drive/images/example_test_output.png)
