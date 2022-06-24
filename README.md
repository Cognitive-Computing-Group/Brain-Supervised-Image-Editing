# Brain-Supervised-Image-Editing
Code and data release for "Brain-Supervised Image Editing", published in proceedings of CVPR 2022 -  [paper](https://openaccess.thecvf.com/content/CVPR2022/html/Davis_Brain-Supervised_Image_Editing_CVPR_2022_paper.html)
# How to use this repository

NOTE: This repository will be updated by August 1st 2022 with additional code and data.

## Prelimaries
### GAN Model
The CelebAHQ trained GAN model used for generation and semantic editing of facial images can be found [here](https://github.com/tkarras/progressive_growing_of_gans) via "Pre-trained networks" under [karras2018iclr-celebahq-1024x1024](https://drive.google.com/drive/folders/15hvzxt_XxuokSmj0uO4xxMTMWVc0cIMU).

### Requirements

#### EEG Signal Classification and Semantic Editing
matplotlib==3.2.2  
numpy==1.18.5  
pandas==1.0.5  
scikit_learn==1.0.2  
scipy==1.6.2  
tqdm==4.47.0  

#### Image Generation
tensorflow-gpu>=1.6.0

## Pipeline
While the authors believe the primary value of this repository stems from the EEG data and associated latents themselves, we have also provided some basic starter code to understand how a basic pipeline may function.

### EEG Signal Classification
The notebook "01 - EEG Classifier" contains full documentation on how to take the modified EEG data (100ms averages to preserve privacy) paired with the labeled stimuli and train an LDA classifier to label stimuli using brain signals.

### Semantic Editing
The notebook "02 - Semantic Editing" contains full documentation on how to take the output labels predicted from the EEG signals paired with the latents used to generate the stimuli and learn to separate semantic features within the GAN model. This feature representation is then used to make semantic changes to the images via modification of their associated latent vectors.

### Image Generation
The notebook "03 - Image Generation" contains full documentation on how to take the modified latent vectors and produce generated images via the GAN model. 