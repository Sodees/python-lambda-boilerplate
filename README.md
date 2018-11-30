# Python Lambda Boilerplate
A simple boilerplate/starter for creating AWS Lambdas in python (python3.3+). This relies on the [python-lambda] module for deployment and managing environment variables. It allows you to run local tests and automatically deploy code to AWS based on local variables

## Version
v1.0.0

## Requirements
Written in python3.7 (compatible back to 3.3)

## Features
- Makefile to run basic commands for building/testing/deploying the Lambda
- Contains unit test scaffoling in /tests
- Includes linting via flake8
- Contains logger and custom error message helpers in /helpers
- Supports TravisCI

## Getting Started

### Installation
1. Create a virtualenv (varies depending on your shell) and activate it
2. Install dependencies via `pip3 install -r requirements.txt`

### Setup Configurations

**Step 1**
After installing dependencies, copy the config.yaml.sample file to config.yaml and modify the relevant values. At a minimum the following settings should be changed:
- function_name
- description
- role

**Step 2**
Uncomment the `environment_variable` blocks in the relevant config files (if necessary) and add environment-specific configuration in those areas

**Step 3**
Modify the included event.json to add to the Records block, which enables the Lambda to be tested locally

### Develop Locally
To run your lambda locally run `make local-run` which will execute the Lambda(initially outputting "Hello, World")

### Deploy the Lambda
To deploy the Lambda be sure that you have completed the setup steps above and have tested your lambda, as well as configured any necessary environment variables.

To run the deployment run `make deply ENV=[environment]` where environment is one of development/qa/production

## Tests
The stock pythin unittest is currently used to provide test coverage and can be run with `make test`

Coverage is used to measure test coverage and a report can be seen by running `make coverage-report`

## Linting
Linting is provided via Flake8 and can be run with `make lint`
