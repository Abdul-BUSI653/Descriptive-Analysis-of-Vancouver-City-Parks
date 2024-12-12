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
The above image displays the DAP design we are implementing for the descyptive analysis.
#### Descriptive  Question for Analysis
![image 001](https://github.com/user-attachments/assets/f33d2ea7-0f6b-4f7a-9238-27cf63efb456)<br>
The above images displays the descryptive analysis of our DAP model.
#### Step 1: Data Ingestion
This step explains about the Data ingestion into AWS Environment
#### Step 2: Data Profiling
This step explain the data profiling in the AWS environment.
#### Step 3: Data Cleaning 
This step explaing the Data cleaning done using the AWS DataBrew service.
#### Step 4: Data Pipeline Design 
This step explain the process of designing a ETL pipeline to transform raw data into structured data.
