# AWS Lambda

Lambda is a compute service that lets you run code without provisioning or managing servers. 
Lambda runs your code on a high-availability compute infrastructure and performs all of the 
administration of the compute resources, including server and operating system maintenance, capacity provisioning and automatic scaling, and logging. 
With Lambda, you can run code for virtually any type of application or backend service.
AWS Lambda supports languages like NodeJS, Java, Python, C# and Go.

## Advantages of using AWS Lambda

- Ease of working with code 
- Multi Language Support (ex : NodeJS, Java, Python, etc)
- Ease of code authoring and deploying
- Log Provision

## Creating a Function

- Click Create function button on the lambda dashboard console.
![Image](https://github.com/sudhan1704/raw_images/blob/main/1.png?raw=true)
- The lambda provides three options to create lambda function.
    - By default, the option is Author from scratch. This option lets you to write the
Lambda code from scratch.It will just have a simple function with helloworld message. 
    - The second option Blueprints gives details of code already written for some of the aws services in languages available
with AWS Lambda. 
    - The third option Serverless Application Repository has the setup of serverless application
which will help to deploy the AWS Lambda code.

![Image](https://github.com/sudhan1704/raw_images/blob/main/2.png?raw=true)

- If we select Author from scratch option, you have to enter function name, runtime and
Role. 
![Image](https://github.com/sudhan1704/raw_images/blob/main/3.png?raw=true)

- Role dropdown has following options:
   - Choose an existing role: This will display all the roles created in the IAM roles.
    - Create new role from template(s): This will allow you to create role and will display permission to be selected for that role. 
    - Create a custom role: This allows the user to create policies as we discussed earlier.

![Image](https://github.com/sudhan1704/raw_images/blob/main/4.png?raw=true)

After selecting the runtime and roles click create function.

## Inline editor

The inline code editor where the code is to be written is as follows:

![Image](https://github.com/sudhan1704/raw_images/blob/main/5.png?raw=true)

The code is written in inline editor by choosing the language of your choice. It allows to choose
the runtime again here. By default, a simple 'hello world' code is written in the inline editor.


By clicking Test button, it will ask for a test event. Name the sample test event with default vaules or select a previously saved test event and click save event.
![Image](https://github.com/sudhan1704/raw_images/blob/main/7.png?raw=true)

Click the test button to see the execution of AWS Lambda
function for the default code.


The output of the execution is displyed as
![Image](https://github.com/sudhan1704/raw_images/blob/main/8.png?raw=true)


# Working example in python using lambda function

## Launching an EC2 instance using lambda function in python

- Write the code to create an ec2 instance in the inline editor.

    - Example code
    
def main():

    import boto3
    
    REGION = 'ap-south-1'        # region to launch instance.
    AMI = 'ami-074dc0a6f6c764218'        # AMI of the Virtual Machine
    INSTANCE_TYPE = 't2.micro'  # instance type to launch.
    EC2 = boto3.resource('ec2', region_name=REGION)

    instance = EC2.create_instances(        # Creating Instance
        ImageId=AMI,
        InstanceType=INSTANCE_TYPE,
        MinCount=1,                         
        MaxCount=1,
        InstanceInitiatedShutdownBehavior='stop', # shutdown behaviour of the EC2 instance
    )

    print ("New Instance Created With ID:",instance[0].instance_id)
    
    EC2.create_tags(Resources=[instance[0].instance_id], Tags=[{'Key':'Name', 'Value':'lambda ec2'}])       #Tag A Name To New Instance
    
    return instance[0].instance_id
    
def lambda_handler(event, context):

    print("New Instance ID: {}".format(main()))
    return None
    
- Deploy the written lambda function and after successfully updating the function, click on the test button to execute the function.

    - Note - Set the timeout according to the execution time required for the lambda function to execute. Make sure the required permissions(roles - ec2 full access) 
  are provided to the created lambda function.
  ![Image](https://github.com/sudhan1704/raw_images/blob/main/10.png?raw=true)
  
- The output of the executed result of the lambda function is as follows :

 ![Image](https://github.com/sudhan1704/raw_images/blob/main/9.png?raw=true)
 
 
 
 
 
 
        

































