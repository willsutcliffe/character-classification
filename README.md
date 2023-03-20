# character-classification

## Overview

The goal of this project was to develop a classification up for hand drawn characters of the the Cyrillic, Hiragana and Katakana alphabets. 

I trained CNNs with and without data augmentation for the various hand drawn characters considered acheiving aroun 97-99\% validation accuracy.
I built a streamlit app allowing a user to practice drawing various characters with the CNN giving a prediction for the top 3 most likely characters 
drawn. 

## Motivation

The motivation for this project came from the fact that I personally spent some time learning these alphabets given my passion for languages
and the fact that I am working on a Japanese experiment. 

## Data

The dataset for hand-drawn cyrillic letters was taken from https://github.com/bolattleubayev/cmnist, which consists of around 121,234 samples of 42 Cyrillic letters. I only used capitalized and none capitalized cyrillic letters from the Russian alphabet.

<p float="left">
  <img src="images/cyrillic2.png" width="600" />
</p>

For Japanese I utilized data from the ETL character database for both Hiragana and Katakana alphabets. In order to read the data I used the tool on github, which I highly recommend, https://github.com/CaptainDario/ETLCDB_data_reader

I trained with X Hiragana and Y Katakana characters, which were each of size 64x64.

## Data processing and loading

For processing the datasets I tried two approachs.
* **no data augmentation** - here the data was resized with Pillow to 64x64, converted to numpy arrays and the images were normalized by 255. Next the tensor data loader of pytorch was used.
* **with data augmentation** - here the image files were stored in folders for train, test, validation and each class label. This allows the image folder data loader of pytorch to be used. In addition data augmentation transformations such as random rotations and tranlations were included. 

## Models

The final CNN model architecture is summarised below:


Dropout is used for regularization. 


## Results

| Alphabet           | TrainAccurac |
| -----------        | ----------- |
| Cyrillic (caps)    | Title       |
| Cyrillic (no caps) | Text        |

## Other exploration 

Mention siamese network and GANs
