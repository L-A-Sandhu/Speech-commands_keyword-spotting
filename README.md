# Speech Command Recognition

## A Keras implementation of neural attention model for speech command recognition

This repository presents a recurrent attention model designed to identify keywords in short segments of audio. It has been tested using the Google Speech Command Datasets (v1 and v2).
For a complete description of the architecture, please refer to  the (https://arxiv.org/abs/1808.08929). 
The Demo notebook is preconfigured with a set of tasks: ```['12cmd', 'leftright', '35word', '20cmd']```. Each of these refer to how many commands should be recognized by the model. When loading the Google Speech Dataset, the user should also select which version to download and use by adjusting the following line:

```gscInfo, nCategs = SpeechDownloader.PrepareGoogleSpeechCmd(version=1, task = '35word')```

The rest of the repository is divided as follows.

* Requirements
* Cloning this repository
* Pre-trained Model 
* Coustom Traning 

## Requirements 
Install the requirements using 
```
pip install -r requirements.txt
```

## Cloning this repository

- Download or clone this repository;
- Open the Demo notebook;
- Choose how many words should be recognized and the Google Speech Dataset version to use;
- Run training and tests.

## Pre-trained Model

If you want a pretrained model, `model-attRNN.h5` contains pre-trained weights for task 35word, version=2.



## Coustom Traning

If you want to train with your own data:

- Use the ```audioUtily.py WAV2Numpy``` function to save your WAV files in numpy format. This speeds up loading considerably;
- Create a ```list_IDs``` array containing the paths to all the numpy files and a ```labels``` array with corresponding labels (already converted to integers);
- Instantiate a ```SpeechGenerator.py SpeechGen``` class;
- Create your own Keras model for audio classification or use one provided in ```SpeechModels.py```;
- Train the model.
