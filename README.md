# Img2Coloring

This repository contains scripts, data and models for the Img2Coloring task - turning an RGB picture into a coloring book.

## Structure:
- *datasets/*</br>
Folder with datasets of this project

- *model/*</br>
Folder with saved weights of trained GAN Pix2Pix model on anime data and Img2LineDrawings. To get trained models also visit this Kaggle dataset: https://www.kaggle.com/datasets/kerrit/img2coloring-pix2pix-trained-models

- *ColoringBook_filters_and_Style_Transer.ipynb*</br>
Scripts for task with convolutional filters, and style transfer for Img2Coloring

- *Multicue_dataset_preprocessing.ipynb*</br>
Scripts to complete multicue dataset in better common format, with merged lines from different annotators.

- *pix2pix_GAN_Training.ipynb*</br>
Script to train pix2pix model for Img2Coloring task. Already trained models (from 12 and 20 epoch) can be loaded from *models/* folder.

- *Transform_images_with_InstructPix2Pix_and_Img2Drawings.ipynb*</br>
Scripts to transform local images in "slonik" (kids) style with already pretrained models.

## Datasets
- Multicue dataset</br>
https://serre-lab.clps.brown.edu/resource/multicue/

This dataset is realistic photo dataset with edges maps from different annotators. This edges not strict, so in this scripts multicue dataset was preprocessed to merge edges for same photos between annotators (in Multicue_dataset_preprocessing.ipynb). Final result - dataset "border_dataset.zip" in "datasets" folder.  

Typical image and merged borders from this dataset:
![borders_dataset_1.png](sample_images/borders_dataset_1.png)
![borders_dataset_2.png](sample_images/borders_dataset_2.png)

- BIPED dataset</br>
https://www.kaggle.com/datasets/xavysp/biped

Dataset with realistic photos with edges, annotations for this photos is bad for Img2Coloring task, but can be helpfull in other cases.

- AbsKids datasets </br>
*datasets/AbsKidsImg2Line.zip*</br>
*datasets/AbsKidsTextImg2Line.zip*</br>
*datasets/AbsKidsOtherImg2Line.zip*</br>

Inner dataset with images in kids style with RGB format. These images was target images for Img2Coloring task.

- Anime Sketch Colorization Pair</br>
https://www.kaggle.com/datasets/ktaebum/anime-sketch-colorization-pair

Dataset for anime sketches colorizations. In this projects it can be used in reverse task, to uncolorize (make a coloring book style, in some interpretation) source anime images.

## Samples

This is samples for different approaches for Img2Coloring task.

### Filters
Default convolutional filters for edge detections. </br>
Canny filter
![Canny1](sample_images/canny_1.png)
![Canny2](sample_images/canny_2.png)
</br>
Sobel filter
![Sobel1](sample_images/sobel_1.png)
![Sobel2](sample_images/sobel_2.png)

### Pretrained models
Results for pretrained "Img2LineDrawings" model:
![Img2LineDrawings](sample_images/Img2LineDrawings.png)
Results for pretrained "ControlNet" model:
![ControlNet](sample_images/control_net.png)

### Trained own Pix2Pix model
Results for anime and kids images for own Pix2Pix model (from epoch 12). </br>
Anime images samples:
![pix2pixanime](sample_images/pix2pix_trained_anime.png)
Kids images samples:
![pix2pixkids](sample_images/pix2pix_trained_kids.png)
Kids images 2 samples:
![pix2pixkids](sample_images/pix2pix_trained_kids2.png)



