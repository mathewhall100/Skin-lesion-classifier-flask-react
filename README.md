# Skin Lesion Classifier 
## Deep learning model deployed as a web app using flask and react

<img src="images\skin_app_image_1.PNG" width="400">

[App](https://skin-lesion-web-classifier.herokuapp.com/)

## Model

Images of benign and malignant skin lesions were downloaded from the ISIC Skin Lesion Archive (https://www.isic-archive.com) and pre-processed using ImageMagick. A densenet161 model was trained on 5000 images using the fastai deep learning library (https://docs.fast.ai/) and validated on a subset of 20% total images. The model achieved an acccuracy of 88% correctly classifying benign from malignant lesions. 

The model achieved 88% accuracy on a validation set
Of the misscklassified lesions: 
* 76 out of 423 malignant melanoma were missclassified as benign nevi
* 44 out of 594 benign nevi were missclassified as malignant melanoma 

This gives a sensitivity and specificity of: 

* sensitivity: 82.0%
* specificity: 92.6%

[More details at docs\1_training.md](.\docs\1_training.md)

## Disclaimer


Note that this app is not FDA approved, nor is it endorsed by any physician or hospital. It is intended for experiment and demonstration purposes only and should not be used to provide any medical guidance or advice whatsoever.



## To run locally

1) Clone repo to local computer.
2) Note that the densenet model file (model.pkl) is too large to push to github repo so it is stored in github releases. You will need to create a 'models' folder in the app root directory and then download classes.txt and moel.pkl from github/releases to the models folder where the app can find them.
3) Go to app.py. Make sure the code for 'local deployment' is uncommented and the code for 'heroku deployment' is commented out. 
4) Install dependencies - torch==1.1.0, torchvision==0.2.1, Flask==1.0.2,  fastai==1.0.54. It is important to install the correct versions as they must match exactly the versions used to create the model.pkl file otherwise version errors may result. The quickest way to install the dependencies is to run the following from the command line: 
```
    pip install -r requirements.txt
```
5) Then start the app from within the app's src directory:
```
    python app.py
```

## Instructions

Either click on a test image in the left hand panel, or upload an image of your own using the 'upload' button. 

The image will appear in the image frame. Click 'predict' to begin the prediction. It can take up to 30 seconds to run the image through the model and the result with probablity is displayed in the results pane on the right. 

## Citation Note

> Data obtained from https://www.isic-archive.com/

>Code based on Pattaniyil, Nidhin and Shaikh, Reshama, [Deploying Deep Learning Models On Web And Mobile](https://reshamas.github.io/deploying-deep-learning-models-on-web-and-mobile/), 2019




 


 

 
 
 
