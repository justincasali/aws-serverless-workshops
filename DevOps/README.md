# Serverless DevOps Workshop

In this workshop you'll deploy a RESTful API that enables users to manage the Wild Rydes Unicorn Stable.  You will use the [Serverless Application Model (SAM)](https://github.com/awslabs/serverless-application-model) to deploy the API interfaces, business logic, and database into your AWS account.  The RESTful API will allow a user to list, create, view, update, and delete the unicorns in the Wild Rydes stable.

The application architecture uses [AWS Lambda](https://aws.amazon.com/lambda/), [Amazon API Gateway](https://aws.amazon.com/api-gateway/), and [Amazon DynamoDB](https://aws.amazon.com/dynamodb/).  The API is built using Lambda and API Gateway, using DynamoDB as a persistent data store for unicorn data.

See the diagram below for a depiction of the API architecture.

![Wild Rydes DevOps RESTful API Application Architecture](images/wildrydes-devops-api-architecture.png)

The DevOps Continuous Delivery Pipeline uses [AWS CodePipeline](https://aws.amazon.com/codepipeline/), [AWS CodeBuild](https://aws.amazon.com/codebuild/), and [Amazon S3](https://aws.amazon.com/s3/).  CodePipeline orchestrates the steps to build, test, and deploy your code changes.  CodeBuild compiles source code, runs tests, and produces software packages that are ready to deploy to environments.

See the screenshot below for a depiction of the continuous delivery pipeline that you will build at the completion of Module 4.

![Wild Rydes Unicorn API Continuous Delivery Pipeline](images/codepipeline-final.png)

If you'd like to jump in and get started please visit the [CodeStar Project](0_CodeStar) module page to begin the workshop.

## Pre-requisites

### AWS Account

In order to complete this workshop you'll need an AWS Account with access to create AWS IAM, Cloud9, S3, DynamoDB, Lambda, API Gateway, CodePipeline, and CodeBuild resources. The code and instructions in this workshop assume only one student is using a given AWS account at a time. If you try sharing an account with another student, you'll run into naming conflicts for certain resources. You can work around these by appending a unique suffix to the resources that fail to create due to conflicts, but the instructions do not provide details on the changes required to make this work.

All of the resources you will launch as part of this workshop are eligible for the AWS free tier if your account is less than 12 months old. See the [AWS Free Tier page](https://aws.amazon.com/free/) for more details.

### AWS Cloud9 IDE

To complete the first module of this workshop you'll need the AWS Cloud9 IDE deployed in your AWS account. You'll use the AWS CLI embedded in the AWS Cloud9 IDE to copy objects into your S3 website bucket.

AWS Cloud9 is a cloud-based integrated development environment (IDE) that lets you write, run, and debug your code with just a browser. It includes a code editor, debugger, and terminal. Cloud9 comes pre-packaged with essential tools for popular programming languages and the AWS Command Line Interface (CLI) pre-installed so you don’t need to install files or configure your laptop for this workshop. Your Cloud9 environment will have access to the same AWS resources as the user with which you logged into the AWS Management Console.

Take a moment now and setup your Cloud9 development environment.

✅ Step-by-step Instructions

Go to the AWS Management Console, click **Services** then select **Cloud9** under Developer Tools.

Click **Create environment**.

Enter **Development** into **Name** and optionally provide a **Description**.

Click **Next step**.

You may leave **Environment settings** at their defaults of launching a new **t2.micro** EC2 instance which will be paused after **30 minutes** of inactivity.

Click **Next step**.

Review the environment settings and click **Create environment**. It will take several minutes for your environment to be provisioned and prepared.

Once ready, your IDE will open to a welcome screen. Below that, you should see a terminal prompt similar to:

![Wild Rydes Unicorn API Continuous Delivery Pipeline](images/setup-cloud9-terminal.png)

You can run AWS CLI commands in here just like you would on your local computer. Verify that your user is logged in by running **`aws sts get-caller-identity`**.

You’ll see output indicating your account and user information:

~~~~
Admin:~/environment $ aws sts get-caller-identity

{
    "Account": "123456789012",
    "UserId": "AKIAI44QH8DHBEXAMPLE",
    "Arn": "arn:aws:iam::123456789012:user/Alice"
}
~~~~

Keep your AWS Cloud9 IDE opened in a tab throughout this workshop as you’ll use it for activities like running AWS SAM and the AWS CLI.

### Browser

We recommend you use the latest version of Chrome or Firefox when testing the web application UI.


## Modules

This workshop is broken up into multiple modules. You must complete each module before proceeding to the next.

0. [CodeStar Project](0_CodeStar)
1. [Serverless Application Model (SAM)](1_ServerlessApplicationModel)
2. [Continuous Delivery Pipeline](2_ContinuousDeliveryPipeline)
3. [AWS X-Ray Integration](3_XRay)
4. [Multiple Environment CI/CD Pipeline](4_MultipleEnvironments)


After you have completed the workshop you can delete all of the resources that were created by following the [cleanup guide](9_CleanUp).
