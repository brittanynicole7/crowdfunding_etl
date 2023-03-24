# Crowdfunding ETL

# Project Description 

## Part 1: Create the Category and Subcategory DataFrames

### Extract and transform crowdfunding.xlsx and create a Category DataFrame.
- Create a "category_id" column that has entries going from "cat1" to "catn", where n is the number of unique categories.
- Create a category column that has the titles.
- Export the Category DataFrame as a csv file.

### Extract and transform crowdfunding.xlsx and create a Subcategory DataFrame.
- Create a "subcategory_id" column that has entries going from "subcat1" to "subcatn", where n is the number of unique subcategories.
- Create a subcategory column that has the titles.
- Export the Subcategory DataFrame as a csv file. 

## Part 2: Create the Campaign DataFrame
- Extract and transform the crowdfunding.xlsx and create a Campaign DataFrame.
- Rename the blurb, launched_at, and deadline columns.
- Convert the goal and pledged columns to a 'float' data type.
- Format the launched_date and end_date columns to datetime format. 
- Merge the campaign_df with with the category_df on the "category" column and the subcategory_df on the "subcategory" column.
- Drop unwanted columns.
- Export the DataFrame to a csv file. 

## Part 3: Create the Contacts DataFrame
- Iterate through the contact_info_df and convert each row to a dictionary.
- Create a contact_info DataFrame and add the contact_id, name, and email columns.
- Split the first name and last name into two columns and drop the name column.
- Reorder the columns (contact_id, first_name, last_name, email).
- Export the DataFrame as a csv file. 

## Part 4: Create the Crowdfunding Database
- Create an ERD using QuickDBD. 
- Create a table schema for each csv file.
- Save the file as a Postgres file.
- Create a new database called crowdfunding_db.
- Create the tables in the correct order.
- Run a select statment for each table to verify that the table was created.
- Import each csv file into its SQL table.
- Verify that each table has correct data by running a select statement. 

# Software and Files
## For Parts 1-3
- import pandas as pd
- import numpy as np
- pd.set_option('max_colwidth', 400)

## Part 1: Create the Category and Subcategory DataFrames
- 'Resources/crowdfunding.xlsx'
- "Resources/category.csv"
- "Resources/subcategory.csv"

## Part 2: Create the Campaign DataFrame
- from datetime import datetime as dt
- "Resources/campaign.csv"

## Part 3: Create the Contacts DataFrame
- 'Resources/contacts.xlsx'
- import json
- "Resources/contacts.csv"

## Part 4: Create the Crowdfunding Database
- SQL
- Quick DBD


# Output/Analyses

## Part 1: Create the Category and Subcategory DataFrames

- Got the crowdfunding_info_df column names.
<img width="1063" alt="Screenshot 2023-03-22 at 10 07 27 PM" src="https://user-images.githubusercontent.com/119909433/227090663-e3711c58-acb6-4acb-a331-345cce2545a4.png">

- Split the categories and subcategories into two separate columns.
<img width="1060" alt="Screenshot 2023-03-22 at 10 09 14 PM" src="https://user-images.githubusercontent.com/119909433/227091253-36efe341-1c2f-41ec-bc1b-c2be9e4d4963.png">

- Got the unique categories and subcategories in separate lists.
<img width="944" alt="Screenshot 2023-03-22 at 10 09 46 PM" src="https://user-images.githubusercontent.com/119909433/227091429-a9e2a4b0-e112-4708-97af-db316f1fbfa2.png">

- Printed the length of the distinct values in the category and subcategory columns. 
<img width="1052" alt="Screenshot 2023-03-22 at 10 10 16 PM" src="https://user-images.githubusercontent.com/119909433/227091601-b6f30195-dc63-4ef4-96b4-b9237da24f22.png">

- Created arrays from 1-9 for the categories and 1-24 for the subcategories.
<img width="1052" alt="Screenshot 2023-03-22 at 10 10 54 PM" src="https://user-images.githubusercontent.com/119909433/227091832-126417ed-ad26-446a-a13f-791e4873d7d0.png">

- Used list comprehension to add "cat" to each category_id and "subcat" to each subcategory_id.
<img width="1055" alt="Screenshot 2023-03-22 at 10 11 44 PM" src="https://user-images.githubusercontent.com/119909433/227092107-e80696c3-892d-4f39-8a3b-5534f6a30b21.png">

- Created category and subcategory DataFrames.
<img width="1051" alt="Screenshot 2023-03-22 at 10 12 18 PM" src="https://user-images.githubusercontent.com/119909433/227092259-dd69289a-8f51-4213-b612-398b6d9d9402.png">
<img width="1057" alt="Screenshot 2023-03-22 at 10 12 30 PM" src="https://user-images.githubusercontent.com/119909433/227092284-5913f797-9429-4077-ab64-b2deed20dbd8.png">
<img width="1057" alt="Screenshot 2023-03-22 at 10 12 41 PM" src="https://user-images.githubusercontent.com/119909433/227092312-78fa8fe3-aa27-49b6-ad13-ea86ff27abfe.png">

- Exported the DataFrames to csv files. 
<img width="1051" alt="Screenshot 2023-03-22 at 10 13 11 PM" src="https://user-images.githubusercontent.com/119909433/227092411-49b57a74-dab2-4eae-ae55-9caa6f0e7a65.png">


## Part 2: Create the Campaign DataFrame

- Renamed columns. 
<img width="935" alt="Screenshot 2023-03-23 at 8 54 32 PM" src="https://user-images.githubusercontent.com/119909433/227404408-4facc9a1-1987-433e-8244-dd7f7b738e93.png">

- Converted columns to "float" data types. 
<img width="908" alt="Screenshot 2023-03-23 at 8 55 16 PM" src="https://user-images.githubusercontent.com/119909433/227404499-4791b657-d062-4a21-913b-98813054e736.png">

- Converted columns to datetime format.
<img width="916" alt="Screenshot 2023-03-23 at 8 55 49 PM" src="https://user-images.githubusercontent.com/119909433/227404547-d7529b35-cde0-4d34-b14d-45850cbe3686.png">

- Merged the campaign, category, and subcategory DataFrames.
<img width="927" alt="Screenshot 2023-03-23 at 8 56 22 PM" src="https://user-images.githubusercontent.com/119909433/227404607-89c02c09-a3f5-4a86-bcbd-9263ec2328a1.png">

- Dropped unwanted columns. 
<img width="1159" alt="Screenshot 2023-03-23 at 8 56 52 PM" src="https://user-images.githubusercontent.com/119909433/227404660-54ac5e9f-6408-4c4f-a73c-50424f33fa42.png">

- Exported the DataFrame as a csv file.
<img width="1150" alt="Screenshot 2023-03-23 at 8 57 16 PM" src="https://user-images.githubusercontent.com/119909433/227404717-9e64725c-a4d1-4541-a6d7-2f267645e025.png">

## Part 3: Create the Contacts DataFrame

- Iterated through the contact_info_df and converted each row to a dictionary.
<img width="1045" alt="Screenshot 2023-03-22 at 10 14 19 PM" src="https://user-images.githubusercontent.com/119909433/227092562-ec732234-ecaf-4781-90a0-5e5458f005c5.png">

- Created a contact_info DataFrame with contact_id, name, and email columns.
<img width="1049" alt="Screenshot 2023-03-22 at 10 15 06 PM" src="https://user-images.githubusercontent.com/119909433/227092698-8356a116-7dc2-4187-b5ea-a5ef335f1631.png">

- Created a first and last name column and dropped the name column. 
<img width="1049" alt="Screenshot 2023-03-22 at 10 15 46 PM" src="https://user-images.githubusercontent.com/119909433/227092794-eaa7ab82-4461-436f-9537-d6ecb1e3a951.png">

- Redordered the columns.
<img width="1062" alt="Screenshot 2023-03-22 at 10 16 13 PM" src="https://user-images.githubusercontent.com/119909433/227092865-7149ed6c-148f-412a-8c06-7fd578355286.png">

- Exported the DataFrame as a csv file.
<img width="1052" alt="Screenshot 2023-03-22 at 10 16 43 PM" src="https://user-images.githubusercontent.com/119909433/227092955-df1a07de-32ab-49fc-8edf-240f72b6ab5e.png">

## Part 4: Create the Crowdfunding Database
- Created an ERD for the csv files. 
<img width="721" alt="Screenshot 2023-03-23 at 8 58 06 PM" src="https://user-images.githubusercontent.com/119909433/227404815-64d93c23-ce2e-4c85-b080-1850d0cb3b28.png">

- Exported the SQL file for the table schema and used it to create tables in SQL. 
<img width="538" alt="Screenshot 2023-03-23 at 8 58 58 PM" src="https://user-images.githubusercontent.com/119909433/227404918-9d3f0f9f-a3d4-4dca-ac88-ceb644cf6335.png">
<img width="769" alt="Screenshot 2023-03-23 at 8 59 32 PM" src="https://user-images.githubusercontent.com/119909433/227404986-d896421a-2e6c-4660-9d59-a20066324683.png">

- Imported csv files and displayed tables.
<img width="1098" alt="Screenshot 2023-03-23 at 8 33 39 PM" src="https://user-images.githubusercontent.com/119909433/227405196-ee36e274-84d7-41a8-a143-fecd6480d32a.png">
<img width="1117" alt="Screenshot 2023-03-23 at 8 34 10 PM" src="https://user-images.githubusercontent.com/119909433/227405210-edd743e7-1515-4414-9b60-caff6475df11.png">
<img width="1114" alt="Screenshot 2023-03-23 at 8 34 32 PM" src="https://user-images.githubusercontent.com/119909433/227405217-97a2bdeb-68b3-404a-b09d-c907a872457e.png">
<img width="1108" alt="Screenshot 2023-03-23 at 8 34 52 PM" src="https://user-images.githubusercontent.com/119909433/227405226-b50c5f41-8bf3-4df2-9a8d-e52e9e0cf429.png">


# Authors 
- Brittany Wright github:brittanynicole7
- Karen Fuentes github:kfuentes0205
