# GitHub Actions-Salesforce Integration Guide

This guide outlines the steps to integrate GitHub Actions, a workflow automation tool provided by GitHub, with Salesforce, a leading CRM platform. By integrating GitHub Actions with Salesforce, you can automate various tasks like testing and source code deployment from one org to another.

## Prerequisites

- Salesforce: Have access to a Salesforce Developer Hub org and necessary permissions to create Connected Apps.
- GitHub: Have your Salesforce project hosted on GitHub for version control.

## Setup JWT Flow to Integrate GitHub Actions with Salesforce

1. **Create Connected App for JWT-Based Flow:**
   - Log in to your Salesforce Developer Hub org.
   - Navigate to Setup > App Manager > New Connected App.
   - Fill out the required information, including Callback URL (can be any valid URL), and enable OAuth settings.
   - Make sure to select "Use digital signatures" and "Enable for Device Flow" checkboxes.
   - Save the Connected App and note down the Consumer Key.

2. **Configure Environment Variables in GitHub:**
   - Set the following environment variables in GitHub Secrets:
     - **SF_CONSUMER_KEY_DEV**: The Consumer Key generated for the Connected App in Developer Org.
     - **SF_CONSUMER_KEY_PROD**: The Consumer Key generated for the Connected App in Production Org or the org where you want to deploy the code.
     - **SF_USERNAME_DEV**: The username for the Salesforce Developer Hub org.
     - **SF_USERNAME_PROD**: The username for the Salesforce Production org or the org where you want to deploy the code.
     - **SERVER_KEY_PASSWORD**: The password used to encrypt the server.key.enc file.

## Connecting to GitHub using SSH

1. Generate SSH key pair:
   - Generate an SSH key pair using `ssh-keygen`.
2. Add SSH public key to GitHub:
   - Copy the public key generated in the previous step.
   - Add it to your GitHub account's SSH keys.
3. Test the SSH connection:
   - Run `ssh -T git@github.com` to verify the SSH connection to GitHub.

