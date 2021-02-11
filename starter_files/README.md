

# Operationalizing Machine Learning
The goal of this project is to operationalize a Machine Learning project. First, an automated Machine Learning pipeline will be executed, deployed and consumed. The used dataset concerns bank marketing used for a classification problem. Automated Machine Learning and Python SDK is used in this project. Automated Machine Learning (AutoML) automates Machine Learning development. 

## Architectural Diagram
![PROJECT 2](https://user-images.githubusercontent.com/54527456/107497465-e8333780-6b92-11eb-8497-f09d30ac2b5c.JPG)
The architectural diagram comprises a couple of steps. The first step is to upload the dataset to be used in the Machine Learning algorithm. Thereafter, several Machine Learning algorithms to solve the classification problem are applied in the Automated Machine Learning step. In the third step, when the Automated Machine Learning has finished, the best performing model in terms of accuracy is chosen to be deployed. Azure Container Instance is used for deployment and authentication is applied. Application insights is 'activated' and the documentation is 'activated' using Swagger. The deployed model is consumed by executing a file named endpoint.py. To obtain output, the script has to be executed.


## Key Steps
Below the key steps will be described with additional screenshots to depict the key steps. 

# Step 2: AutoML experiment 
To retrieve the best model, first multiple models have to be run. AutoML allows for running multiple models to find the best performing model. 

In the screenshots the uploaded dataset, the completed experiment, and the best model from that experiment is shown. 

![Screenshot (2)](https://user-images.githubusercontent.com/54527456/107620400-e9c53400-6c54-11eb-9dc4-e24ba77bc44d.png)
![Screenshot (3)](https://user-images.githubusercontent.com/54527456/107620404-ea5dca80-6c54-11eb-82d0-f59a90683764.png)
![Screenshot (4)](https://user-images.githubusercontent.com/54527456/107620405-ea5dca80-6c54-11eb-9708-ab86d298499b.png)
![Screenshot (5)](https://user-images.githubusercontent.com/54527456/107620406-eaf66100-6c54-11eb-802a-e45c129989b6.png)


# Step 3: Deploy best model
Deployment delivers a trained model into production and creates several options to consume the model. The end result after deploying a model is an HTTP endpoint. In the screenshot the result of deploying a model is shown (depicted with 'Completed' with a green icon).

![Screenshot (7)](https://user-images.githubusercontent.com/54527456/107620527-1d07c300-6c55-11eb-8394-b7a3401c5a4c.png)


# Step 4: Enable logging
Application Insights is a tool to detect anomalies, visualize performance, and is enabled in this step. The screenshots show that Application Insights is enabled and logs by running the logs.py script. 

![Screenshot (16)](https://user-images.githubusercontent.com/54527456/107620647-52141580-6c55-11eb-849a-22b312a646dd.png)
![Screenshot (14)](https://user-images.githubusercontent.com/54527456/107620649-52acac00-6c55-11eb-83e2-df1116f934f4.png)
![Screenshot (15)](https://user-images.githubusercontent.com/54527456/107620650-52acac00-6c55-11eb-9c4c-aff2924dcf35.png)

# Step 5: Swagger documentation 
Swagger is a tool that helps build, document, and consume RESTful web services like deployed earlier. A requirement to apply Swagger is to have Docker installed. RESTful is a style for building HTTP endpoints that emphasizes separation of concerns. Several HTTP requests exist, including POST and GET, can be consumed by an API. A website can be created with the swagger.json file, provided by Azure. This website documents the HTTP endpoints for a deployed model.

Two scripts are necessary. First, a Python server has to be initiated with the serve.py script. Now, in the localhost in the browser the contents of the directory can be found. This script enables CORS in order to allow Swagger to build locally documentation. 

Thereafter, the most recent Swagger container needs to be downloaded, via the swagger.sh. If localhost in the browser is now visited, Swagger is running from the container by the previous step. Using the following link in the top bar http://localhost:8000/swagger.json should now display the contents of the API for the deployed model. Using the swagger.json file in the Swagger UI shows the available endpoints with demo inputs. 

The screenshots show the contents of the API, and the screenshots show that swagger runs on localhost showing the HTTP API and responses for the model.

![Screenshot (9)](https://user-images.githubusercontent.com/54527456/107620821-9acbce80-6c55-11eb-8da3-50743699ceaf.png)
![Screenshot (10)](https://user-images.githubusercontent.com/54527456/107620822-9b646500-6c55-11eb-9ea3-891c7193aba5.png)
![Screenshot (11)](https://user-images.githubusercontent.com/54527456/107620823-9b646500-6c55-11eb-96f3-c2cee0939bac.png)
![Screenshot (12)](https://user-images.githubusercontent.com/54527456/107620825-9b646500-6c55-11eb-826c-8b5461f8874d.png)

# Step 6: Consume model endpoint
Once a model is deployed, it can be consumed via an HTTP API. An API is a software intermediary that allows two applications to talk to each other. So interaction with a trained (deployed) model can occur via an HTTP request via an HTTP API, which is an URL exposed over the network. Often an input requist is initiated via an HTTP POST request to submit data. HTTP GET request retrieves information from a URL. The provided endpoint.py script needs the scoring_uri and (primary) key from the Consume tab in the Endpoints section. Running this script creates a POST request to the deployed model to get a response printed in the terminal. The screenshot shows that the endpoint.py script runs against the API producing JSON output from the model. 

![Screenshot (46)](https://user-images.githubusercontent.com/54527456/107620946-c9e24000-6c55-11eb-858c-e2afa31731b6.png)


# Step 7: Create, Publish, and Consume a pipeline
Pipelines can include several steps (including AutoML). A pipeline can be published. A public HTTP endpoint becomes then available, allowing other services, including external ones, to interact with an Azure Pipeline. The pipeline endpoint can be consumed via HTTP, Python SDK or other options. The screenshots show the pipeline section of Azure ML studio, which shows that the pipeline has been created and the pipeline endpoint. Also the Jupyter Notebook is shown in the screenshot where 'use rundetails widget' shows the step runs. 

![Screenshot (60)](https://user-images.githubusercontent.com/54527456/107621309-5260e080-6c56-11eb-99f6-9ae7c3523cd8.png)
![Screenshot (61)](https://user-images.githubusercontent.com/54527456/107621341-63115680-6c56-11eb-8038-8ae57d6bca30.png)
![Screenshot (47)](https://user-images.githubusercontent.com/54527456/107621392-77555380-6c56-11eb-85c9-8b00d88cc996.png)
![Screenshot (62)](https://user-images.githubusercontent.com/54527456/107621571-c00d0c80-6c56-11eb-97d5-3ef5cd1faaaf.png)
![Screenshot (63)](https://user-images.githubusercontent.com/54527456/107621635-dc10ae00-6c56-11eb-8346-5de03fc465f3.png)
![Screenshot (26)](https://user-images.githubusercontent.com/54527456/107646204-fc9e2f80-6c79-11eb-98fa-a138aea7b1d5.png)




## Screen Recording
https://youtu.be/T-6zzHCohQU

## Future Improvement Suggestions 
- The dataset is imbalanced. This can be fixed by for instance creating more data of the smallest class (in case of classification problem).
- Other Machine Learning models can be experimented with.
- Accuracy is currently used. However, other performance metrics exist to define the model's performance. In future work different performance metrics can be used.
