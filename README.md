# CNN Sentiment Analysis Model
## End-to-end Training and Deployment on AWS (Amazon Web Service)

<br>

The model is deployed on AWS API Gateway. 

https://yggy8xxbo4.execute-api.us-east-1.amazonaws.com/v1/predict

With any tweet sentence input, it will output the overall sentiment of the sentence.

For example:

input: {"tweet" : "No one knows python better than me."}

output: {"Sentiment": "positive"}

<br>

***raw-data.zip***: unprocessed data, split into three subsets

Link to the raw dataset on the S3: https://aiops-2020-public.s3.us-east-2.amazonaws.com/training.full.csv

* `train.csv`
* `dev.csv`
* `eval.csv`

<br>

***lambda-function***
* `my_lambda_pre_processor.py`: lambda function
* pre_processing: Python library for preprocessing
    - `word_embedding.py`: load embedding dictionary
    - `text_processing.py`: clean and tokenize text
    - `pre_processing.py`: pre-process tweets
    - `nltk_tokenize.py`: nltk tokenizer library
    - resources
      - `glove.txt`: embedding dictionary (without vector)
      
<br>

***aws-glue-job***
* `glue_preprocessing_job_script.py`: script for Glue ETL job
* `glue-job-output`: processed data
    * `train.json`
    * `dev.json`
    * `eval.json`

<br>

***sagemaker_jupyter_code.ipynb***: jupyter notebook used to train model on AWS SageMaker Notebook

<br>

***model_training***
* `sentiment_dataset.py`: load datasets
* `training_config.json`: store the value of model parameters
* `sentiment_model_cnn.py`: define the CNN model
* `sentiment_training.py`: pass in arguments and train the model

<br>

***model-saved***: the final version of the trained model



