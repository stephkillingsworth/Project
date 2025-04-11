## Project_AI_Biology
## Maria (Belu) Ugarte Marin and Stephanie Killingsworth

## Introduction

The data for this model include 2D images of the occlusal (chewing surface) of upper and lower first and second molars from three different extinct species of horse. The images were taken using a portable lightbox setup and Nikon CoolPix600 camera while visiting various paleontology collections representing different quarries found in North America. The aim of this project is to groundtruth whether smaller image datasets of less than 200 images per class can still produce CNN models with adequate accuracy. The significance of this test pertains to the common issue in the field of paleontology of small sample sizes. Here we use horse tooth datasets of *Dinohippus interpolatus*, *Dinohippus mexicanus*, and *Equus simplicidens*, to perform several iterations for testing small datasets. These closely related species have small variations in their tooth morphology (characters) that we hope to distinguish through CNN models to potentially detect modes of speciation and paleo-population dynamics to clarify how and where *Equus*, modern horse, may have originated.

For this project, we use two approaches: 
Approach 1: Uses upper and lower molars from each species to train a model to predict the species class (Dinohippus interpolatus, Dinohippus mexicanus, and Equus simplicidens).
Approach 2: Uses only upper or lower molars from from each of the species to train a model to predict the species class (Dinohippus interpolatus, Dinohippus mexicanus, and Equus simplicidens).

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

## Hyperparameter Tuning

## Results

## Discussion
