# Data-engineering-project
Moving data from public API to Azure.


## Moving data from Public API to a Data Lake.
>
>This can be done by building a data pipeline manually, usually a Python script (you can leverage a tool as Apache Airflow for this) or using Airbyte using the following steps;
>
* Set up Rest Api as a source connector (using Auth, or  an API key).
* Set up AWS Datalake as a destination connector.
* Define which data you want to transfer and how frequently.

Airbyte is an open-source data integration platform that consolidates and streamlines the process of extracting and loading data from multiple data sources to data warehouses. It offers pre-built connectors, including Rest Api and AWS Datalake, for seamless data migration.

When using Airbyte to move data from Rest Api to AWS Datalake, it extracts data from Rest Api using the source connector, converts it into a format AWS Datalake can ingest using the provided schema, and then loads it into AWS Datalake via the destination connector. This allows businesses to leverage their Rest Api data for advanced 
analytics and insights within AWS Datalake, simplifying the ETL process and saving significant time and resources.

# Step 1: Set up Rest Api as a source connector
![image](https://github.com/Parq254/Data-engineering-project/assets/61014329/6a538106-94ba-488c-b826-52ba7f3fa2ab)

1. Open the Airbyte platform and navigate to the "Sources" tab on the left-hand side of the screen.

2. Click on the "Add Source" button and select "Rest Api" from the list of available connectors.

3. Enter a name for your Rest Api source and click on the "Next" button.

4. In the "Connection Configuration" section, enter the base URL for your Rest Api endpoint.

5. If your Rest Api requires authentication, select the appropriate authentication method (Basic, OAuth2, or API Key) and enter the necessary credentials.

6. If your Rest Api requires additional headers or query parameters, enter them in the "Additional HTTP Headers" and "Additional Query Parameters" sections, respectively.

7. Click on the "Test" button to ensure that your Rest Api source is properly configured and that Airbyte can connect to it.

8. If the test is successful, click on the "Create" button to save your Rest Api source and begin syncing data.

9. You can now configure your Rest Api source to specify which data to sync, how often to sync it, and where to send it.

# Step 2: Set up AWS Datalake as a destination 

![image](https://github.com/Parq254/Data-engineering-project/assets/61014329/e6d7ff67-269a-4893-864a-bc993c7112a5)
1. Log in to your AWS account and navigate to the AWS Management Console.
2. Click on the S3 service and create a new bucket where you will store your data.
3. Create an IAM user with the necessary permissions to access the S3 bucket. Make sure to save the access key and secret key.
4. Open Airbyte and navigate to the Destinations tab.
5. Select the AWS Datalake destination connector and click on "Create new connection".
6. Enter a name for your connection and paste the access key and secret key you saved earlier.
7. Enter the name of the S3 bucket you created in step 2 and select the region where it is located.
8. Choose the format in which you want your data to be stored in the S3 bucket (e.g. CSV, JSON, Parquet).
9. Configure any additional settings, such as compression or encryption, if necessary.
10. Test the connection to make sure it is working properly.
11. Save the connection and start syncing your data to the AWS Datalake.

# Step 3: Set up a connection to sync your Rest Api data to AWS Datalake
![image](https://github.com/Parq254/Data-engineering-project/assets/61014329/2a69bc40-ee8e-445b-b092-201320b18c1a)
> Once you've successfully connected Rest Api as a data source and AWS Datalake as a destination in Airbyte, you can set up a data pipeline between them with the following steps:

1. ***Create a new connection:** On the Airbyte dashboard, navigate to the 'Connections' tab and click the '+ New Connection' button.
3. ***Choose your source:*** Select Rest Api from the dropdown list of your configured sources.
4. ***Select your destination:*** Choose AWS Datalake from the dropdown list of your configured destinations.
5. ***Configure your sync:*** Define the frequency of your data syncs based on your business needs. Airbyte allows both manual and automatic scheduling for your data refreshes.
6. ***Select the data to sync:*** Choose the specific Rest Api objects you want to import data from towards AWS Datalake. You can sync all data or select specific tables and fields.
8. ***Select the sync mode for your streams:*** Choose between full refreshes or incremental syncs, and this for all streams or at the stream level. Incremental is only available for streams that have a primary cursor.
10. ***Test your connection:*** Click the 'Test Connection' button to make sure that your setup works. If the connection test is successful, save your configuration.
11. ***Start the sync:*** If the test passes, click 'Set Up Connection'. Airbyte will start moving data from Rest Api to AWS Datalake according to your settings.

# How to ensure security and reliability of the data pipeline.

1. ***Encryption and Hashing***
Encryption converts your data into an unreadable format that can only be decrypted with a key, while hashing generates a unique and irreversible value for each data item. By using encryption and hashing, you can prevent data breaches, ensure data integrity, and comply with data privacy regulations.

2. ***Implementing authentication and authorisation***
Authentication verifies the identity of the users or systems that access your data pipeline, while authorization determines the level of access and permissions they have. By implementing authentication and authorization, you can control who can access, modify, or delete your data, and enforce the principle of least privilege. You can use various methods to implement authentication and authorization, such as passwords, tokens, certificates, roles, and policies.

3. ***Monitor and audit data pipeline***
Monitoring helps you detect and respond to any anomalies, errors, or threats in your data pipeline, such as unauthorized access, data loss, or performance degradation. Auditing helps you track and record the actions and events that occur in your data pipeline, such as data sources, transformations, destinations, and users. By monitoring and auditing your data pipeline, you can ensure its availability, reliability, and accountability.

4. ***Use secure tools and framework***
Secure tools and frameworks can help you automate and simplify your data pipeline processes, such as data ingestion, transformation, validation, and delivery. They can also help you implement security features, such as encryption, hashing, authentication, authorization, monitoring, and auditing. Some examples of secure tools and frameworks for data pipeline engineering are Apache Airflow, Apache NiFi, AWS Glue, and Azure Data Factory.

5. ***Update and test pipeline***
Updating your data pipeline helps you fix any bugs, vulnerabilities, or compatibility issues that may affect your data pipeline functionality or security. Testing your data pipeline helps you verify its functionality, performance, and security, and identify any errors or weaknesses that may compromise your data quality or integrity. You can use various tools and methods to update and test your data pipeline, such as version control, automated testing, and code review.




















