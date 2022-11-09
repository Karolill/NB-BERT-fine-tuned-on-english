# NB-BERT fine-tuned on English

This project explores if a language model that is mostly pre-trained on Norwegian (NB-BERT) can learn down-stream tasks by fine-tuning on English. 

The project consist of the following files:
- `model.ipynb` which contains the code to load, fine-tune and evaluate the models. 
- `norec_preprocessing.ipynb` which contains the code to preprocess the NoReC dataset and create the datasets used for this experiment. 

## Prerequisites

To run the code in `norec_preprocessing.ipynb` the following must first be done:
1. The norec dataset must be downloaded from [https://github.com/ltgoslo/norec](https://github.com/ltgoslo/norec). Make sure that the norec folder lies in the same location as norec_preprocessing.ipynb.
This code does not have to be run, as all the datasets created in this script is saved as csv files in this repositry. 

## Model

The file `model.ipynb` is very time-consuming to run. It fine-tunes a total of 5 models. However, to reduce the time a bit it's enough to only fine-tune two models, so the following lines can be commented out:
```
create_and_train_model(3e-5, './model_pretrained_on_imdb_dataset_', final_train_imdb_encoding, final_eval_imdb_encoding)
create_and_train_model(4e-5, './model_pretrained_on_imdb_dataset_', final_train_imdb_encoding, final_eval_imdb_encoding)
create_and_train_model(5e-5, './model_pretrained_on_imdb_dataset_', final_train_imdb_encoding, final_eval_imdb_encoding)
```
