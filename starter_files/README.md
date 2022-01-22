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
   
   # Uploaded data
   ![step2_pic1_dataset](https://user-images.githubusercontent.com/96047873/150637403-d7f6b45b-9434-4f13-a6da-1a71d5149786.png)
   
   # Completed run
   ![step2_pic_2_ML-run](https://user-images.githubusercontent.com/96047873/150637576-23533116-06e5-4b1e-ae7e-4a790a6c6664.PNG)


2) Best model is deployed with authentification enabled and using "Azure Container Instance (ACI)".

   # Endpoint section
   ![step4_pic1_ApplicationInsights](https://user-images.githubusercontent.com/96047873/150637607-7a1bc560-6148-4a66-b042-4d66d05f735d.png)


4) Enabling Logging/Application Insights via a script (logs.py). This could also be done via azure when deploying the model.
   
   # Logs
   ![step4_pic2_logs](https://user-images.githubusercontent.com/96047873/150637651-720a5a42-a779-4eb3-8c93-eeb37f7a772f.png)
  
  
5) Swagger documentation using the Swagger-URL provides by Azure for the deployed model.

   # Swagger
   ![step5_pic1_swagger1](https://user-images.githubusercontent.com/96047873/150637660-0bd94a8e-7c34-40ad-beff-052776b2ca3e.png)
   ![step5_pic2_swagger2](https://user-images.githubusercontent.com/96047873/150637664-c82ea25b-9cfd-45bd-96d4-25b125ff94a8.png)


6) Consumption of model endpoint by using the endpoint.py script. Here the URL and a key for the deployed model have to be used to authenticate.
   I am having an issue here. The forum suggested that the order of the keys in JSON have to be the same as in Azure. However, this did not work for me.
   To show that the endpoint could be consumed, I ran the benchmark. This worked with the same JSON.

# Issue with endpoint.py
![step6_pic1_consume_error](https://user-images.githubusercontent.com/96047873/150637710-7f877a88-0199-4601-ab8e-75dbce443fcc.png)

# Benchmark as alternative
![step6_pic2_benchmark](https://user-images.githubusercontent.com/96047873/150637722-7c5ca602-f5e9-436e-b290-663ffdbe0fec.png)

7) Creation of a pipeline including a new model training with auto-ML. Then also publishing this pipeline and consuming it.

   # Running pipeline
   ![step7_pic1_pipeline](https://user-images.githubusercontent.com/96047873/150637759-723834d9-9ae2-425c-acfc-bc2a948c5746.png)

   # Completed pipeline runs
   ![step7_pic2_pipelines](https://user-images.githubusercontent.com/96047873/150637785-7b6e5d71-25f7-46d9-8fa6-896dc9cf9fc1.PNG)
   
   # pipeline endpoints
   ![step7_pic3_endpoint](https://user-images.githubusercontent.com/96047873/150637794-8dab5e83-0813-4dfb-a57d-a9a682e1bf65.PNG)
   ![step7_pic4_Pipeline_rest_endpoint](https://user-images.githubusercontent.com/96047873/150637946-f21554ca-f20c-425a-9db2-1d44dcd4ecd5.png)

   # RunDetails output
   ![step7_pic5_bank_autoML_module](https://user-images.githubusercontent.com/96047873/150637943-31d9594f-f624-4756-abf3-6c39fc8c1fc8.PNG)
   
   # Published pipeline overview
   ![step7_pic6_published_pipeline_overview](https://user-images.githubusercontent.com/96047873/150637960-1fcb6b78-ba00-4f2e-ae25-ebef508075a5.PNG)


## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

https://youtu.be/uPRFgUMh9DA


## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
I ran the benchmark.sh script. This worked fine for me. The endpoint.py script did not work even though I think I understand what I have to do there and it worked for me in the exercise. I saw the post about the order of the keys in JSON and tried this as solution. After that I still got the same error and was not able to fix it. 
