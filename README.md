# Image Classification using AWS SageMaker

Use AWS Sagemaker to train a pretrained model that can perform image classification by using the Sagemaker profiling, debugger, hyperparameter tuning and other good ML engineering practices. This can be done on either the provided dog breed classication data set or one of your choice.

## Project Set Up and Installation
Enter AWS through the gateway in the course and open SageMaker Studio. 
Download the starter files.
Download/Make the dataset available. 

## Dataset
The provided dataset is the dogbreed classification dataset which can be found in the classroom.
The project is designed to be dataset independent so if there is a dataset that is more interesting or relevant to your work, you are welcome to use it to complete the project.

### Access
Upload the data to an S3 bucket through the AWS Gateway so that SageMaker has access to the data. 

## Hyperparameter Tuning
What kind of model did you choose for this experiment and why? Give an overview of the types of parameters and their ranges used for the hyperparameter search
I used a pretrained resnet50 model
i used these parameters: lr, batch_size, epochs and their ranges:
    "lr": ContinuousParameter(0.001,0.1),
    "batch_size": CategoricalParameter([32,64,128,256,512]),
    "epochs": IntegerParameter(2,4)

After tuning i find theses valuees: 
'batch_size': 32,
'epochs': 4,
'lr': 0.06271147221173151,

i also use AdamW in my training script
 #reference https://androidkt.com/pytorch-adamw-and-adam-with-weight-decay-optimizers/
 
 
Remember that your README should:
- Include a screenshot of completed training jobs
- Logs metrics during the training process
- Tune at least two hyperparameters
- Retrieve the best best hyperparameters from all your training jobs

## Debugging and Profiling
**TODO**: Give an overview of how you performed model debugging and profiling in Sagemaker
 i used hook in training script to log some information

### Results
**TODO**: What are the results/insights did you get by profiling/debugging your model?
i see that the batch size is to small and the instance type chosen memory is too small

**TODO** Remember to provide the profiler html/pdf file in your submission.


## Model Deployment
**TODO**: Give an overview of the deployed model and instructions on how to query the endpoint with a sample input.
i use this link to write the inference script  and use some recomandations suggested by the link:
https://sagemaker.readthedocs.io/en/stable/frameworks/pytorch/using_pytorch.html#deploy-pytorch-models


**TODO** Remember to provide a screenshot of the deployed active endpoint in Sagemaker.

## Standout Suggestions
**TODO (Optional):** This is where you can provide information about any standout suggestions that you have attempted.
