# Image Segmentation fastai Unet
This implementation uses fastai's UNet model, where the CNN backbone (e.g. ResNet) is pre-trained on ImageNet and hence can be fine-tuned with only small amounts of annotated training examples.

Different default parameters under MODEL_TYPE are provided for either a smaller model, or a deeper and wider model, which tends to have higher accuracy but can be a magnitude slower to train and run inference.

## Data
In this notebook, we use a toy dataset specified in DATA_PATH which consists of 129 images of 4 classes of beverage containers {can, carton, milk bottle, water bottle}. For each image, a pixel-wise ground-truth mask is provided for training and evaluation.

You'll notice that DATA_PATH contains two subfolders and one file:
* /images
* /segmentation-masks
* classes.txt

This is a common data structure for image segmentation. The two folders use the same filename to indicate which mask corresponds to which image.

The masks in segmentation-masks contain at each pixel the id of the object. In our case, id 0 corresponds to "background", 1 to "can", 2 to "carton", 3 to "milk_bottle" and 4 to "water_bottle". This mapping from id to class name is defined in the file classes.txt.
['background', 'can', 'carton', 'milk_bottle', 'water_bottle']

## Model Performance
![](https://github.com/billumillu/Image-Segmentation-fastai-Unet/blob/main/seg_output1.jpg)

## Test Image
![](https://github.com/billumillu/Image-Segmentation-fastai-Unet/blob/main/seg_output.jpg)
