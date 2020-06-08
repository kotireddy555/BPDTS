# BPDTS - Senior DevOps Role

Deployed API available here : https://lojlh6ocu3.execute-api.eu-west-2.amazonaws.com/dev

I have deployed BPDTS Test application using API Gateway and Lambda functions on AWS Cloud. As part of deployment process I have created following resources and configured api URL header. 

-     API Gateway 

-     Lamda Function (included the required dependencies)

-     IAM Role for CloudWatch logs and Lambda permissions 

**In summary:** Firstly created a lambda function called BPDTS Test application with python runtime and lambda permissions then uploaded .zip to same. Next new api created with required resource headers and mapped with newly created lambda function. At last created api deployment stage and deployed the api and tested manually. 

The reason why I choose server-less(lambda and api gateway) approach is, It is most cost effective, light weight, easy to maintain api and secure(waf, tls1.2), provide authentication and authorisation to the api, request validation, fully integrated with IAM. Moreover we don't need to worry about memory, CPU and network. 

However we can deploy the application using Elastic Beanstalk which will be PaaS approach or docker containers, OfCourse we can also use other cloud service providers. It really depends on use case to use case.

If I have more time and resources I would think at production scale, build and deploy the application using Infrastructure as Code(IaC) which will help us to deploy the application seamlessly and securely.

My aim is to make sure everything automated and no manual interventions required while build, test, code coverage, security vulnerabilities or virus scans and deploy. I will use 

-   Terraform will use for IaC as it will support for multi cloud service providers 

-   Use terraform workspaces to deploy in different environments and integrate with GitHub webhooks

-   Secure the application with IP whitelist and store terraform state information 

-   Move the sensitive information to vault/secrets manager

-   Enable api keys and auto rotate same 

-   Configure alarms and trigger the notifications to topics, respective groups or channels(Teams or Slack) 

-   Capture the logs and store it with rotation policy  and versioning enabled.


Though there are many CI/CD tools but the end goal is to automate the entire deployment process with minimal or no interventions. 
