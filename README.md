# Steps to create CI/CD Pipeline for Salesforce 

## Set up OAuth JWT Bearer Token authentication
    Open VS Code in remote repository
    Use openssl to create a self-signed certificate and key
    Use Salesforce Admin interface to set up connected app
    Test local use of authentication flow
    Store self-signed key in repository
## Write the GitHub Action
    Authenticate the current session with Salesforce
    Retrieve the target repository
    Deploy metadata and run unit tests on a production org
## Activate Action with a repository PUSH
    Use GitHub and Salesforce web interfaces to monitor the execution of the Action
