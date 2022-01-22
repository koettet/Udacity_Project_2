*NOTE:* This file is a template that you can use to create the README for your project. The *TODO* comments below will highlight the information you should be sure to include.

# Udacity-Project 2 - Bankmarketing

*TODO:* Write an overview to your project.

This project is about deploying trained models to make them ready for consumption. This also includes model documentation via swagger and model benchmarketing to keep track of the models performance and possible issues like failed requests.
On more step is then done with creating a pipeline that includes retaining the model in this case. THis pipeline is then also deployed and published so it can be started via http even fromn outside of Azure.

## Architectural Diagram
*TODO*: Provide an architectual diagram of the project and give an introduction of each step. An architectural diagram is an image that helps visualize the flow of operations from start to finish. In this case, it has to be related to the completed project, with its various stages that are critical to the overall flow. For example, one stage for managing models could be "using Automated ML to determine the best model". 

## Key Steps
*TODO*: Write a short discription of the key steps. Remeber to include all the screenshots required to demonstrate key steps. 

1) Creating an auto-ML run including uploading the data for training, creating a compute cluster and configuring auto-ML.
   Result: trained best model ready for deployment.
   
2) Best model is deployed with authentification enabled and using "Azure Container Instance (ACI)".
3) Enabling Application Insights via a script (logs.py). This could also be done via azure when deploying the model.
4) Swagger documentusing the Swagger-URL provides by Azure for the deployed model.
5) Consumption of model endpoint by using the endpoint.py script. Here the URL and a key for the deployed model have to be used to authenticate.
   I am having an issue here. The forum suggested that the order of the keys in JSON have to be the same as in Azure. However, this did not work for me. To show that    the endpoint could be consumed, I ran the benchmark. This worked with the same JSON.
6) Creation of a pipeline including a new model training with auto-ML. Then also publishing this pipeline and consuming it.  

## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

https://youtu.be/uPRFgUMh9DA

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
I ran the benchmark.sh script. This worked fine for me. The endpoint.py script did not work even though I think I understand what I have to do there and it worked for me in the exercise. I saw the post about the order of the keys in JSON and tried this as solution. After that I still got the same error and was not able to fix it. 
