# Descriptive-Analysis-of-Vancouver-City-Parks
A project which explain on the DAP design and implementation for the descriptive analysis of the "Parks" segment of city of Vancouver.

* The dataset taken by me is about the  “Parks” segment of the “Parts, Recreation and Pets” module of the Vancouver city portal.
* In this we have key features like the ‘Park Name’, ‘Special Features’, ‘Facilities’, ‘Washroom’,  ‘Address’ and other details.
* From this, the main objective the teammate has taken to do analysis is “What is the count of parks in each ‘Neighbourhood’ of Vancouver recorded with a Washroom facility?”.
* Using this, we can further analyze the population segmentation around these areas and other details.
* Data Questions (Metric)
First we need to gather a few details below:
•	Total count of parks in each neighborhood
•	Total count of parks in each neighborhood with washroom facility
•	Find the ration of the parks with washroom to the total count of parks in each neighbourhood respectively.
#### Data Questions (Metric)
First we need to gather a few details below:
* Total count of parks in each neighborhood
* Total count of parks in each neighborhood with washroom facility
* Find the ration of the parks with washroom to the total count of parks in each neighbourhood respectively.<br>
Below I mentioned the 4 step process involved in the DAP design related to the descriptive question posted above analysis (highlighted and underlined).<br>
We are going to use the AWS services like S3, Glue, Glue DataBrew as per our need to store the results and other details of the project.
#### Dap Design
![image 000](https://github.com/user-attachments/assets/4121d110-4bfd-4b89-bfa0-93d88a47e082)<br>
* The above image displays the DAP design we are implementing for the descyptive analysis.
#### Descriptive  Question for Analysis
![image 001](https://github.com/user-attachments/assets/f33d2ea7-0f6b-4f7a-9238-27cf63efb456)<br>
* For the initial part we need to choose the dataset on which we are going to do analysis on.
* In my case I took the “Parts, Recreation and Pets” module of the Vancouver city portal.
* The above figure displays the analysis shown based on the conditions set in the Vancouver portal.
* The above images displays the descryptive analysis of our DAP model.
#### Step 1: Data Ingestion
* This step explains about the Data ingestion into AWS Environment.
* We have downloaded the dataset as an excel file which we will be moving to the ‘S3’ buckets of AWS.
* Prior to this we created a bucket called “vprp-raw-abdul” in that he created a folder called ‘Ingestion_year-2024’ to store the information of year 2024.
* Now we have the S3 bucket and folder to ingest our dataset into it. I then uploaded the dataset into the folder.
![image 003](https://github.com/user-attachments/assets/06cca1f5-7388-47a3-8f3a-b3aaefa58cf2)<br>
* Above image displays the final end results of the ingestion.
#### Step 2: Data Profiling
* This step explain the data profiling in the AWS environment.
* Now using Data profiling we will understand the structure of the data so as we can maintain the quality standards.
* For this we first need to understand the various columns and their data-type we will be using in the analysis.
![image 004](https://github.com/user-attachments/assets/e3b1c55d-1b5d-4e5a-9aaa-6eba2ed07432)<br>
* We can also understand the information of the data stored in the dataset like the meta information, the data types of each column data and other information related to dataset here.
* For this we run the ‘Data Profiling’ job available after creating the dataset “Vancouver-park-dataset-abdul” in AWS Glue DataBrew.
![image 006](https://github.com/user-attachments/assets/0287d559-8bf5-4d27-938e-0e4f5436ac0e)<br>
* The above indicates the results generated by the data profiling job.
* From above we can see that there are some cells which have missing values.
* We will now move on to clean and structure the data for further usage.
#### Step 3: Data Cleaning 
* This step explaing the Data cleaning done using the AWS DataBrew service.
* To start with the cleaning first he created a project called “vancouver-park-dataset-cleaningproject-abdul” in ‘AWS Glue DataBrew.
![image 007](https://github.com/user-attachments/assets/3765aa49-2e9e-47e6-83e3-0bf4e2c8d51e)<br>
* The above images displays all the cleaning job details we are going to implement.
![image 008](https://github.com/user-attachments/assets/c24f8fc9-f26a-4321-8b01-683eaed37f92)<br>
* We can see the job created by implementing all the changes mentioned in the above cleaning process for each column respectively.
![image 009](https://github.com/user-attachments/assets/585e1477-75b4-42f2-9830-cd15ea76cdbe)<br>
* The end results after running the cleaning job are stored in the ‘tmp’ folder under the ‘Data-Cleaning’ folder inside the ‘vprp-tfm-abdul’ bucket inside S3. The results are displayed as above.
#### Step 4: Data Pipeline Design 
* This step explain the process of designing a ETL pipeline to transform raw data into structured data.
* We can now move to the final stage of creating the ETL pipeline for the dataset selected to do the descriptive analysis of our part.
* For this we will use AWS Glue service, I created the ETL named “vrpr-parks-pip-abdul” in AWS Glue.
![image 010](https://github.com/user-attachments/assets/0fe0b77e-755a-4d29-a266-723489ad19a7)<br>
* From above pipeline information you can see that first I loaded the information of parks into the console I then dropped unwanted columns and only selected those I need.
* I then segregated into two one where I filtered the parks for those having washroom facility and then fond count of those in each neighbourhood.
* For the other part I just found the total count of parks in each neighbourhood.
* Next I joined these two segregations by merging using the ‘Join’ function.
* I then used a new function of derived column to find the percentage of parks with washroom in each neighbourhood and then stored the details using the ‘with washroom’ and ‘neighbourhood’ partitions.
![image 011](https://github.com/user-attachments/assets/647be45b-492f-4764-97aa-ff233b2d6bad)<br>
* Above image shows the output of the pipeline in generated to calculate the percentage of parks with washrooms in each neighbourhood.
![image 012](https://github.com/user-attachments/assets/27b66a7a-a52e-4ce6-a5e8-8f5c09747961)<br>
* Above images shows the job run details.
![image 013](https://github.com/user-attachments/assets/b77101e3-02ca-4006-af11-cf6e15db6c5f)<br>
* Above image displays the resulted stored in the ‘neighbourhood’ folder using the partition key.
![image 014](https://github.com/user-attachments/assets/6a9bdf05-402e-4669-8db2-0582c7fb7fc9)<br>
* Above image displays the resulted stored in the ‘with washroom’ folder using the partition key.
