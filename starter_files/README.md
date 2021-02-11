

# Operationalizing Machine Learning
The goal of this project is to operationalize a Machine Learning project. First, an automated Machine Learning pipeline will be executed, deployed and consumed. The used dataset concerns bank marketing used for a classification problem. Automated Machine Learning and Python SDK is used in this project. Automated Machine Learning (AutoML) automates Machine Learning development. 

## Architectural Diagram
![PROJECT 2](https://user-images.githubusercontent.com/54527456/107497465-e8333780-6b92-11eb-8497-f09d30ac2b5c.JPG)
The architectural diagram comprises a couple of steps. The first step is to upload the dataset to be used in the Machine Learning algorithm. Thereafter, several Machine Learning algorithms to solve the classification problem are applied in the Automated Machine Learning step. In the third step, when the Automated Machine Learning has finished, the best performing model in terms of accuracy is chosen to be deployed. Azure Container Instance is used for deployment and authentication is applied. Application insights is 'activated' and the documentation is 'activated' using Swagger. The deployed model is consumed by executing a file named endpoint.py. To obtain output, the script has to be executed.


## Key Steps
*TODO*: Write a short discription of the key steps. Remeber to include all the screenshots required to demonstrate key steps. 

# Step 2: AutoML experiment 
![Screenshot (2)](https://user-images.githubusercontent.com/54527456/107620400-e9c53400-6c54-11eb-9dc4-e24ba77bc44d.png)
![Screenshot (3)](https://user-images.githubusercontent.com/54527456/107620404-ea5dca80-6c54-11eb-82d0-f59a90683764.png)
![Screenshot (4)](https://user-images.githubusercontent.com/54527456/107620405-ea5dca80-6c54-11eb-9708-ab86d298499b.png)
![Screenshot (5)](https://user-images.githubusercontent.com/54527456/107620406-eaf66100-6c54-11eb-802a-e45c129989b6.png)

# Step 3: Deploy best model
![Screenshot (7)](https://user-images.githubusercontent.com/54527456/107620527-1d07c300-6c55-11eb-8394-b7a3401c5a4c.png)

# Step 4: Enable logging

# Step 5: Swagger documentation 

# Step 6: Consume model endpoint

# Step 7: Create, Publish, and Consume a pipeline


## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
- The dataset is imbalanced. This can be fixed by for instance creating more data of the smallest class (in case of classification problem).
- Other Machine Learning models can be experimented with.
- Accuracy is currently used. However, other performance metrics exist to define the model's performance. In future work different performance metrics can be used.
