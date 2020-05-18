# FAU-Ditylum-Identification
Using TensorFlow to build a model that autonomously identifies and counts the marine diatom called ditylum from images taken from divers at FAU.

## STEP 1 - Clean Images
For this step we use the function "dilate" to brighten the highs and lows of the image to reduce some of the noise.

## STEP 2 - Split Images
First we access the "blob log" function that finds regions with pixels in common i.e. blobs. With those blobs we are able to extract out single regions with properties in common (different diatoms) and split the image into separate images focusing on one diatom. The new image sizes will be 250x250 pixels.

## STEP 3 - Organize
We split the single diatom pictures into labels of "ditylum" or "not ditylum".

## STEP 4 - Reduce Size
We use PCA to take out data that is not useful and will therefore cause the training process to take longer.

## STEP 5 - Train
Using the zoomed in labeled single diatom pictures we are able to train a dataset of around 400 or so images. For the first try, we are using logistic regression.

Ways to improve the model
Get rid of more noise by using different cleaning functions on the data.
Try slightly different scales of the images (not just 250x250px).
Utilize Keras/Tensorflow (great for deep learning), try different keras models: VGG16, VGG19, ResNet50, InceptionV3, DenseNet, etc.
Change the hyperparameters of the different models to yield better results. Can also utilize the lambda machine and/or cloud services to train on larger dataset.

Other Models Tried:
* K-nearest Neighbors with elbow method to find the optimal K value - BEST SO FAR
* Convolutional Neural Net
