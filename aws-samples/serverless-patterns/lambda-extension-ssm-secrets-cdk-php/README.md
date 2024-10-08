# Lambda extension to cache SSM and Secrets Values for PHP Lambda on CDK

This pattern demonstrates how to access and caches SSM Parameter Store and Secrets Manager values from a PHP Lambda using 
Lambda extension.

To know more about PHP Lambdas, visit https://bref.sh.

Learn more about this pattern at Serverless Land Patterns: https://serverlessland.com/patterns/

Important: this application uses various AWS services and there are costs associated with these services after the Free 
Tier usage - please see the [AWS Pricing page](https://aws.amazon.com/pricing/) for details. You are responsible for any AWS costs incurred. No 
warranty is implied in this example.

## Requirements

* [Create an AWS account](https://portal.aws.amazon.com/gp/aws/developer/registration/index.html) if you do not already have one and log in. The IAM user that you use must have sufficient permissions to make necessary AWS service calls and manage AWS resources.
* [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) installed and configured
* [Git Installed](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [AWS Cloud Development Kit](https://docs.aws.amazon.com/cdk/latest/guide/cli.html) (AWS CDK) installed
* [Docker](https://docs.docker.com/engine/install/) installed (which will install PHP, composer, Node, NPM, CLI and CDK) -- this is optional if you have everything installed

## Deployment Instructions

1. Create a new directory, navigate to that directory in a terminal and clone the GitHub repository:
    ``` 
    git clone https://github.com/aws-samples/serverless-patterns
    ```
1. Change directory to the pattern directory:
    ```
    cd lambda-extension-ssm-secrets-cdk-php
    ```
1. Make sure you have already AWS variables set and run below command to install required dependancies:
   ```shell
   # Using docker -- check run-docker.sh
   make up
   ```
   or
   ```shell
   # Using local
   npm ci
   cd php && composer install --no-scripts && cd -
   ```
1. From the command line, run:
   ```shell
   # Using docker
   make deploy
   ```
   or
   ```shell
   # Using local
   npm run deploy
   ```
1. Alternatively, you can jump into the container and deploy from inside:
   ```sh
   make bash
   npm run deploy
   ```

## Testing

* Execute the Lambda function and you will see the parameter value as output.

## Cleanup
 
1. To delete the stack, run:
    ```bash
    make bash
    npm run destroy
    ```
----
Copyright 2024 Amazon.com, Inc. or its affiliates. All Rights Reserved.

SPDX-License-Identifier: MIT-0
