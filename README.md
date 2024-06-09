# This project aims to provide some guidence on Fine tuning LLMs

## Tools

+ **Jupyter Notebook**
+ **Cohere**: Provides some powerful LLMs, free and limited API requests for researchers. [Cohere](https://cohere.com/)
+ **HuggingFace**: A platform with huge amount of open-source LLMs, DataSets and so on. [Huggingface](https://huggingface.co/)
+ **Docanno**: A tool for labeling the dataset and can be used to build instruction + output for training. [Docanno](https://github.com/doccano/doccano) 

## General Steps
1. **Find the Data Source** :You can take advantage of some open source data, or Crawling some data on the Internet (Please note the legality). 

2. **Pre-processing the dataset**: Filter the data from the data source, leave only the information needed for further processing or training. Better to structure it to some structured format(e.g. json).

​		

​		Use LLMs to help:

+  *pre-processing_data/MT_Filter_5TEs_Huggingface.ipynb* : This file provides an example to use the model on huggingface to help with processing data.
+ *pre-processing_data/MT_Filter_ISO_Cohere.ipynb* : This file provides an example to use the model provided by cohere to processing data.

3. **Processing the dataset**: Before training, you need to build you own dataset for training, typically including *Instruction + Output*. Docanno can be used as a tool.

+ *processing_data/convert_dataset_to_train.ipynb* : This file provides an example of converting the dataset to the format of the model needed.
+ *processing_data/convert_jsonL.ipynb*: This file provides an example of modifying dataset directly using json.
+ *processing_data/split_dataset_to_train_test.ipynb*: This file provides an example of spliting the dataset into the training set and test set.

4. **Training model（Fine Tuning）**: After build your own dataset, you can start to fine tune a pre-trained model (choose an instruct pre-trained model from HuggingFace).

+ *training_model*: This folder provides some examples to train the model using LoRA and upload the final model to HuggingFace.

5. **Evaluation**: After training the model, you can start evaluation, some metrics can be find in [metrics](https://github.com/huggingface/evaluate/tree/main/metrics):

+ *evaluation_scripts/predicting_with_models*: This folder provides some examples for predicting with the final model.(Either use GPU or Inference API in HuggingFace)
+ *evaluation_scripts/evaluation_metric.ipynb*: Gives an example of evaluation


### Other scripts
+ visualization.ipynb: Some template to Visualize data.
+ CheckData.py: Check the data in the dataset.
+ try_final_model.ipynb: Check if the trained model meets expectations.

Author: 0YHR0





