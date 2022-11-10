# NB-BERT fine-tuned on English

This project explores if a language model that is mostly pre-trained on Norwegian (NB-BERT) can learn down-stream tasks by fine-tuning on English. To do this, five models were created: four of these were fine-tuned on the [IMDB dataset](https://huggingface.co/datasets/imdb) with different learning rate (to check if the learning rate affected the results much, which is didn't), and the last one is fine-tuned on the NoReC dataset with the learning rate that gave the best result on the IMDB dataset. The best model on the IMDB-dataset (from now on named the [IMDB-model](https://huggingface.co/karolill/nb-bert-finetuned-on-imdb?text=I+like+you.+I+love+you)) and the model fine-tuned on the NoReC dataset (hereby named the [NoReC-model](https://huggingface.co/karolill/nb-bert-finetuned-on-norec?text=I+like+you.+I+love+you)) were uploaded to huggingface so they can be loaded more easily. 

The project consist of the following files:
- `model.ipynb` which contains the code to load, fine-tune and evaluate the models. I would recommend to read the comments and text in this file carefully, as it contains tips and tricks for code that can be removed or replaced to run the code faster. 
- `norec_preprocessing.ipynb` which contains the code to preprocess the NoReC dataset and create the datasets used for this experiment. 

## Prerequisites

To run the code in `norec_preprocessing.ipynb` the following must first be done:
1. The norec dataset must be downloaded from [https://github.com/ltgoslo/norec](https://github.com/ltgoslo/norec). Make sure that the norec folder lies in the same location as norec_preprocessing.ipynb.
This code does not have to be run, as all the datasets created in this script is saved as csv files in this repositry. 

## Model

The file `model.ipynb` is very time-consuming to run. It fine-tunes a total of 5 models. However, to reduce the time it takes to run, the models from huggingface can be loaded from there instead of having to be created and saved locally. If this is done, you will not run the code that compares different learning rates, but this file also contains the results from when I ran the code, so you can look at those instead. The code to perform evaluation on the NoReC dataset using the IMDB- and NoReC-model can still work if you read the comments in the code and replace the code where it is suggested. 
