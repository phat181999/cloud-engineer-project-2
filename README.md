### Project Title - Deploy a high-availability web app using CloudFormation

This folder provides the starter code for the "ND9991 - C2- Infrastructure as Code - Deploy a high-availability web app using CloudFormation" project. This folder contains the following files:

#### final-project-starter.yml

Students have to write the CloudFormation code using this YAML template for building the cloud infrastructure, as required for the project.

#### server-parameters.json

Students may use a JSON file for increasing the generic nature of the YAML code. For example, the JSON file contains a "ParameterKey" as "EnvironmentName" and "ParameterValue" as "UdacityProject".

In YAML code, the `${EnvironmentName}` would be substituted with `UdacityProject` accordingly.

At the file create.sh and update.sh can choose either region use-west-1 or region use-west-2

Explain: + At the infrastructure-server-parameters.yml file"

Parameter: It contains the list of parameters that are being used in the current CloudFormation template. Parameters should be declared above your Resources.
Defined following propoties: - Parameter Name - You can provide the name of your choice - Description - A textual value - Type - Identifies the data type of the parameter, such as String or a Number - Default (optional) - Presents the default value of the parameter - AllowedValues (optional) - Presents the list of all possible values.
Resources: Declare at least one resource( a VPC and an internet gateway) -> Name: - It is a string value representing the resource name. You can use a name of your choice/ Resource type: - The resource type identifies the type of resource that you are declaring. For example, Type: AWS::EC2::VPC creates a VPC./ Resource properties: - The resource Properties field has further sub-fields that are specific to each type of resource
Outputs:

create stack cloudformation:

aws cloudformation create-stack --stack-name ourdemoinfra --template-body file://server.yml --parameters file://network.json --region=us-east-1

aws cloudformation describe-stacks

./create.bat InstaUdagramProject server.yml network.json

./update.bat InstaUdagramProject server.yml network.json

./destroy.bat InstaUdagramProject

login aws
aws configure or aws configure set aws_session_token

step create

0. check bucket
   aws s3 ls

1. create bucket name s3
   aws s3 mb s3://{{your-name-s3}} --region "us-east-1"

2.upload file to bucket name created on s3
aws s3 cp --recursive {{your-directory-file-upload}} s3://{{bucket-name-created}} --region "us-east-1"
example: aws s3 cp --recursive C:\Users\ADMIN\OneDrive\Desktop\nd9991-c2-Infrastructure-as-Code-v1\project_starter\website s3://udacity-phatht8 --region "us-east-1"

http://insta-webap-yuonzprhkccs-1406563326.us-east-1.elb.amazonaws.com/
