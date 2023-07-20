# Google Project Factory Input Template
This is an input template for Google Project Setup which outlines the necessary information and configuration options for setting up a new project in Google Cloud Platform. <br><br>
This template includes fields for specifying the project-related details to customize it according to the requirement.

## Prerequisite

1. Organization exist.
2. Management GCP Project exist- Created once per organization to manage other developement team projects.
3. Billing account is setup.
4. Service account from Management project is created and key is added as part of github secrets.
5. Create bucket in Management project with name "tf-state-tw-projects"
6. Below mentioned APIs enabled in management project:

    6.1 Cloud Resource Manager API- To create google cloud resource

    6.2 Cloud Billing API- To associate billing account with project

    6.3 IAM API

    6.4 Cloud Billing Budget API

7. Service Account needs below mentioned permission at org level:

    7.1 Folder Creator - To create Folder

    7.2 Monitoring NotificationChannel Editor - To create budget alert notifcation channel
    
    7.3 Project Creator role - To create project

8. Service Account needs below mentioned permission at billing account level:

    8.1 Billing Account Costs Manager - For setting up budgets

    9.2 Billing Account User & Project Billing Manager- To Associate project with billing account

9. Service account need below permission at management project level:

    9.1 Storage Object Admin- to read the project tf state and update back into the bucket

    

## How to run

1. Create repo using this template
2. Add file with <projectname>.tfvars. To create multiple projects, provide multiple tfvars files.
3. Create service account key(Mgmt Project) and add into the github action secret: GOOGLE_CREDENTIALS
4. Create a PAT token and add in github action secret in variable: GH_ACTIONS_PAT
5. Provide all required values in .tfvars file
6. Run github action
