# Deploying Application Using EC2 Instances in Blue Green Deployment

### [Introduction](https://github.com/sumanth979/AWS_BlueGreenDeployment/blob/master/README.md)

### AWS Resources Invloved:
  * EC2 - Elastic Compute Cloud
  * ASG - Auto Scaling Group
  * ALB - Application Load Balancer
  * Key - AWS Key
  * IAM Roles
  

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

### Input & Output Details:
#### Input
* The inputs for the deployment will be provided 
  * Trough UI if deployment is done using AWS UI.
  * Through **parameters.json** file if the deployment is done using AWS Console.

* The input variable **AppListenerColor** specifies the app deployment mode. (Either Blue or Green).
#### Output
* The Load Balancer DNS details.
<img src="https://github.com/sumanth979/AWS_BlueGreenDeployment/blob/master/Deploying_EC2_Instances/output.png" alt="output">

## Deploy using AWS Console
* To Create the stack details
```
aws cloudformation create-stack --stack-name stackName --template-body file://cf_deployment_template.yaml --role-arn roleARN --parameters file://parameters.json
```
* To describe the stack details (to get the details of stack)
```
aws cloudformation describe-stacks --stack-name stackName > stackDetails.json
```
* To Update the stack details
```
aws cloudformation update-stack --stack-name stackName --role-arn roleARN --parameters file://parameters.json --use-previous-template
```
* To Delete the stack details
```
aws cloudformation delete-stack --stack-name stackName
```
