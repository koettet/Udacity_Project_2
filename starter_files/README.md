*NOTE:* This file is a template that you can use to create the README for your project. The *TODO* comments below will highlight the information you should be sure to include.

# Udacity-Project 2 - Bankmarketing

*TODO:* Write an overview to your project.

This project is about deploying trained models to make them ready for consumption. This also includes model documentation via swagger and model benchmarketing to keep track of the models performance and possible issues like failed requests.
On more step is then done with creating a pipeline that includes retaining the model in this case. THis pipeline is then also deployed and published so it can be started via http even fromn outside of Azure.

## Architectural Diagram
*TODO*: Provide an architectual diagram of the project and give an introduction of each step. An architectural diagram is an image that helps visualize the flow of operations from start to finish. In this case, it has to be related to the completed project, with its various stages that are critical to the overall flow. For example, one stage for managing models could be "using Automated ML to determine the best model". 

# Diagram
![Architectural_Diagram](https://user-images.githubusercontent.com/96047873/150638351-d2cafebe-fa65-4554-8e3a-0ed85be97b41.png)



## Key Steps
*TODO*: Write a short discription of the key steps. Remeber to include all the screenshots required to demonstrate key steps. 

1) I started by creating an Auto-ML run. This includes uploading the bankmarketing data, creating a compute-cluster, defining the model type and finally starting the ML run to obtain models.
   
   # Uploaded data
   ![step2_pic1_dataset](https://user-images.githubusercontent.com/96047873/150637403-d7f6b45b-9434-4f13-a6da-1a71d5149786.png)
   
   # Completed run
   ![step2_pic_2_ML-run](https://user-images.githubusercontent.com/96047873/150637576-23533116-06e5-4b1e-ae7e-4a790a6c6664.PNG)


2) Next, I picked the best model to deploy. I picked the Azure Container instance as Cumpote type for this. Further I chose to enable authentication for secrurity. 

   # Endpoint section
   ![step4_pic1_ApplicationInsights](https://user-images.githubusercontent.com/96047873/150637607-7a1bc560-6148-4a66-b042-4d66d05f735d.png)


3) Then I enabled Application Insights via the logs.py script and took a look at the log output to make sure everything is working.
   
   # Logs
   ![step4_pic2_logs](https://user-images.githubusercontent.com/96047873/150637651-720a5a42-a779-4eb3-8c93-eeb37f7a772f.png)
  
  
4) If you want to know what the model expects as input and how the output should look like, you can use swagger. Azure offers a swagger.json file to download and with the serve.py and the swagger.sh you can take a look at the documentation below. This helps to consome the model.

   # Swagger
   ![step5_pic1_swagger1](https://user-images.githubusercontent.com/96047873/150637660-0bd94a8e-7c34-40ad-beff-052776b2ca3e.png)
   ![step5_pic2_swagger2](https://user-images.githubusercontent.com/96047873/150637664-c82ea25b-9cfd-45bd-96d4-25b125ff94a8.png)


5) To use the model, we can make use of the endpoint.py script to send a post request to our model. For this we need to update the URL and the key for authentication in the script. Both can be found in Azure under the details of the endpoint. Using the script which also contains 2 new sets of data for the model to evaluate we get the following result.

# endpoint.py results
![endpoint_results](https://user-images.githubusercontent.com/96047873/150653967-62235155-47e3-4dc0-aa18-3d33fe97110f.PNG)

6) To make sure our endpoint is also able to handle a bunch of requests, we can benchmark the performance and check if everything is good there. If we update the benchmark.sh script with the information of our endpoint, it will send ten times the two datasets created by endpoint.py and show us if any requests failed and how much time they took.

# Benchmark results
![benchmark_results](https://user-images.githubusercontent.com/96047873/150654031-3678cc80-fa8f-4ba0-9f36-adfc2f56716c.PNG)


7) To automate more steps we can make use of a pipeline. The pipeline makes sens if we expext to retrain the model multiple times. This might make sense if we get new data over time and want to include this in our training. The working pipeline is also published with this notebook: "aml-pipelines-with-automated-machine-learning-step.ipynb". A published pipeline can be used even from outside of Azure.

   # Running pipeline
   ![step7_pic1_pipeline](https://user-images.githubusercontent.com/96047873/150637759-723834d9-9ae2-425c-acfc-bc2a948c5746.png)

   # Completed pipeline runs
   ![step7_pic2_pipelines](https://user-images.githubusercontent.com/96047873/150637785-7b6e5d71-25f7-46d9-8fa6-896dc9cf9fc1.PNG)
   
   # pipeline endpoints
   ![step7_pic3_endpoint](https://user-images.githubusercontent.com/96047873/150637794-8dab5e83-0813-4dfb-a57d-a9a682e1bf65.PNG)
   ![pipeline_endpoint](https://user-images.githubusercontent.com/96047873/150654158-7d895747-5f68-4205-8339-22cb813da112.PNG)
 
   # RunDetails output
   ![step7_pic5_bank_autoML_module](https://user-images.githubusercontent.com/96047873/150637943-31d9594f-f624-4756-abf3-6c39fc8c1fc8.PNG)
   
   # Published pipeline overview
   ![step7_pic6_published_pipeline_overview](https://user-images.githubusercontent.com/96047873/150637960-1fcb6b78-ba00-4f2e-ae25-ebef508075a5.PNG)


## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

https://youtu.be/Q70Mxx-Pp5Y


## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
