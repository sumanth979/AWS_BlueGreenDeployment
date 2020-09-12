# Deploying Application Using EC2 Instances in Blue Green Deployment

### [Introduction](https://github.com/sumanth979/AWS_BlueGreenDeployment/blob/master/README.md)

### Deployment Details:
The Deployment template will contain the creation of the following AWS Resources:
  * Security Group for EC2 Instances
  * Security Group for Load Balancer
  * Application Load Balancer
    * Internet facing
    * Creating Appropriate Target Groups for 
      * blue mode
      * green mode
    * Creating Appropriate Listeners for 
      * blue mode
      * green mode
    * Creating Default Listener based on the Active Mode
  * Creating AutoScaling Group for Blue Mode
    * Creating Appropriate Lauch configuration
  * Creating AutoScaling Group for Green Mode
    * Creating Appropriate Lauch configuration

### Deployment Architecture Diagram:
<img src="https://github.com/sumanth979/AWS_BlueGreenDeployment/blob/master/Deploying_EC2_Instances/Architecture.png" alt="Deployment">

