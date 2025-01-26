# PROJECT OVERVIEW:
1. Data is fetched from a website i.e sports.io. This data is fetched through an API call made directly to the website
2. The raw data is fetched and stored in an S3 bucket.
3. Amazon Glue is used to chreate a database and a schema
4. Amazon Athena is used to query the data via data analytics


## Prerequisites:
1. An API key from sports.io. You must create an account under the website and confirm your email in order to open the launch portal. From there you are able to get the API key
2. NBA endpoint- From the developer portal you can get the link to whatever endpoint you want to access.
3. An AWS account- You require access to the cloudshell and other services to fulfil the project
4. IAM Role/Permissions- Ensure the user or role running the script has the following permissions:
  S3: s3:CreateBucket, s3:PutObject, s3:DeleteBucket, s3:ListBucket
  Glue: glue:CreateDatabase, glue:CreateTable, glue:DeleteDatabase, glue:DeleteTable
  Athena: athena:StartQueryExecution, athena:GetQueryResults

## How to use repo:
1. Sign in to your AWS console
2. At the bottom left of your screen click the Cloudshell icon that opens the cloud terminal
3. Run this code then paste the code from this file:
       nano setup_nba_data_lake.py
4. Find the line of code under #Sportsdata.io configurations that says "api_key" paste your api key inside the quotation. Also edit the bucket name to be unique
5. Press ^X to exit, press Y to save the file, press enter to confirm the file name
6. In the CLI type
      python3 setup_nba_data_lake.py
7. To delete the resources created you can open a new file:
      nano delete_aws_resources.py
8. Copy the code in this file on the repo
9. Exit and run the following
   python3 delete_aws_resources
   
You will find the resources created in the relevant resource pages eg. you will find a bucket created

NOTE: Hardcoding sensitive data is not recommended. The safe approach is to use a .env file to store the sensitive data and editing your setuo_nba_data_lake.py code to load the keys from the .env file

# SKILLS LEARNED:
1. Integrating the serverless querying and data integration services to work seamlessly.
2. Using cloudshell instead of manually performing to creation of services.
3. Integrating external APIs into cloud based workflows.
