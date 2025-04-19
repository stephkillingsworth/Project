## Project_AI_Biology
## Maria (Belu) Ugarte Marin and Stephanie Killingsworth

## Introduction

The data for this model include 2D images of the occlusal (chewing surface) of upper and lower first and second molars from three different extinct species of horse. The images were taken using a portable lightbox setup and Nikon CoolPix600 camera while visiting various paleontology collections representing different quarries found in North America. The aim of this project is to ground truth whether smaller image datasets of less than 200 images per class can still produce CNN models with adequate accuracy. The significance of this test pertains to the common issue in the field of paleontology of small sample sizes. Here we use horse tooth datasets of *Dinohippus interpolatus*, *Dinohippus mexicanus*, and *Equus simplicidens*, to perform several iterations for testing small datasets. These closely related species have small variations in their tooth morphology (characters) that we hope to distinguish through CNN models to potentially detect modes of speciation and paleo-population dynamics to clarify how and where *Equus*, modern horse, may have originated.

For this project, we use two approaches: 
Approach 2A: Uses only lower molars from each of the species to train a model to predict the species class (Dinohippus interpolatus, Dinohippus mexicanus, and Equus simplicidens).
Approach 2B: Uses only uppers molars from each of the species to train a model to predict the species class (Dinohippus interpolatus, Dinohippus mexicanus, and Equus simplicidens).

## Data Pre-Processing

The images were pre-processed using Adobe Photoshop as follows:
- Labeled image uploaded
- Ratio 1:1 set and tooth cropped tight and saved
- Image appearance adjusted for brightness hue as needed
- All images flipped to left-sided tooth orientation
- Background removed and only the occlusal surface of the tooth saved
- Image W X H X Resolution set to 384 X 384 pixels
- Image flattened and exported into a species labeled folder as a .png 

## Model Setup
We used a DenseNet121 model pretrained on ImageNet and transformed the data for training and validation and included augmentation to prevent overfitting by increasing the dataset. We set up a training/validation split, datasets, and loaders to establish three classes (horse species). Weighted decay and regularization functions were added and K-Fold cross-validation performed for 50 epochs until accuracy stopped increasing.

## Hyperparameter Tuning
Several hyperparameter tuning techniques to optimize the performance of the image classification model using DenseNet121 were implemented due to the small dataset. 
Learning Rate: The learning rate is set to 1e-4 for the Adam optimizer.
Weight Decay: A weight decay of 1e-5 is applied to regularize the model and prevent overfitting.
Batch Size: The batch size for training and validation is set to 32 in Approach 2A and 2B.
Data Augmentation: Various data augmentation techniques are used to increase the dataset size and improve generalization:
-Random Resize to 384 X 384 (as opposed to standard 
-Random Grayscale
-Random Rotation (15 degrees)
-Random Affine transformations (small shifts)
Cross-Validation: K-Fold Cross-Validation with 5 splits is used to evaluate the model's performance across different subsets of the data.
Dropout: A dropout rate of 0.5 is applied in the classifier layer to prevent overfitting.
Epochs: The model is trained for 50 epochs in each fold of the cross-validation.
Loss Function: The CrossEntropyLoss is used as the loss function for training the model.
## Results

## Discussion
