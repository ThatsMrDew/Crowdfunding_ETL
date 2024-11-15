# Introduction

    An effective Extract, Transform, Load (ETL) pipeline was created in this project to handle and analyze customer data. The pipeline, which was constructed using Python, Pandas, and PostgreSQL, has advanced data transformation and cleaning features, such as automated data quality assessment, email validation, and phone number normalization. The system inserts the processed data into a PostgreSQL database after processing raw customer data through a number of meticulously planned transformations that produce four different CSV files depending on data quality segments. Comprehensive error handling, thorough logging for monitoring and debugging, and an object-oriented, modular design makes this code expandable and maintainable as some of its key characteristics. The pipeline is appropriate for production settings where data integrity and traceability are essential since it also includes timestamp monitoring and data quality indicators. This project lays the groundwork for more intricate data processing systems while also providing a real-world application of ETL concepts. Below were steps taken to achieve those results:


# The Steps for this mini project are divided into the following subsections:

## 1) Create the Category and Subcategory DataFrames
## 2) Create the Campaign DataFrame
## 3) Create the Contacts DataFrame
## 4) Create the Crowdfunding Database

# Part One: Create the Category and Subcategory DataFrames
## Extracted and transformed the crowdfunding.xlsx Excel data to create a category DataFrame that has the following columns:

A "category_id" column that has entries going sequentially from "cat1" to "catn", where n is the number of unique categories

A "category" column that contains only the category titles

The following image shows this category DataFrame:

![alt text](https://github.com/ThatsMrDew/Crowdfunding_ETL/blob/main/Images/category_df.PNG)

Exported the category DataFrame as category.csv and saved it to our GitHub repository.

Extracted and transformed the crowdfunding.xlsx Excel data to create a subcategory DataFrame that has the following columns:

A "subcategory_id" column that has entries going sequentially from "subcat1" to "subcatn", where n is the number of unique subcategories

A "subcategory" column that contains only the subcategory titles

The following image shows this subcategory DataFrame:

![alt text](https://github.com/ThatsMrDew/Crowdfunding_ETL/blob/main/Images/subcategory_df.PNG)

Exported the subcategory DataFrame as subcategory.csv and saved it to our GitHub repository.

# Part Two: Creating the Campaign DataFrame
## Extracted and transformed the crowdfunding.xlsx Excel data to create a campaign DataFrame that has the following columns:

The "cf_id" column

The "contact_id" column

The "company_name" column

The "blurb" column, renamed to "description"

The "goal" column, converted to the float data type

The "pledged" column, converted to the float data type

The "outcome" column

The "backers_count" column

The "country" column

The "currency" column

The "launched_at" column, renamed to "launch_date" and with the UTC times converted to the datetime format

The "deadline" column, renamed to "end_date" and with the UTC times converted to the datetime format

The "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame

The "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame

Exported the campaign DataFrame as campaign.csv and saved it to our GitHub repository.

# Part Three: Create the Contacts DataFrame
## Both of the following two options for extracting and transforming the data from the contacts.xlsx Excel data:

## Option 1: Uses Python dictionary methods.

## Option 2: Uses regular expressions.

# Option 1, completed the following steps:

Imported the contacts.xlsx file into a DataFrame.

Iterate through the DataFrame, converting each row to a dictionary.

Iterate through each dictionary, doing the following:

Extracted the dictionary values from the keys by using a Python list comprehension.

Added the values for each row to a new list.

Created a new DataFrame that contains the extracted data.

Split each "name" column value into a first and last name, and placed each in a new column.

Cleaned and exported the DataFrame as contacts.csv and saved it to our GitHub repository.

# Option 2, completed the following steps:

Made a copy of Option 1's DataFrame.

Extracted the "contact_id", "name", and "email" columns by using regular expressions.

Created a new DataFrame with the extracted data.

Converted the "contact_id" column to the integer type.

Split each "name" column value into a first and a last name, and placed each into a new column.

Cleaned and then exported the DataFrame as contacts.csv and saved it to our GitHub repository.


# Create the Crowdfunding Database
Inspected the four CSV files, and then sketched an ERD of the tables by using QuickDBDLinks to an external site..
![alt text](https://github.com/ThatsMrDew/Crowdfunding_ETL/blob/main/Images/Crowdfunding_DB_Model.png)

Used the information from the ERD to create a table schema for each CSV file.

Specified the data types, primary keys, foreign keys, and other constraints.

Saved the database schema as a Postgres file named crowdfunding_db_schema.sql, and saved it to our GitHub repository.

Created a new Postgres database, named crowdfunding_db.

Using the database schema, created the tables in the correct order to handle the foreign keys.
    contacts
    category
    subcategory
    campaign

Verified the table creation by running a SELECT statement for each table.

Imported each CSV file into its corresponding SQL table.

Verified that each table has the correct data by running a SELECT statement for each.



# Conclusion: 

Overall, the ETL mini project assigned to us involved extracting, transforming, and loading data from provided Excel files into a Postgres database. We utilized Python, Pandas, and REGEX through Jupyter Notebook in order to process crowdfunding campaign data and create a relational database schema. This project demonstrates our ability to effectively use ETL processes in data manipulation and storage scenarios while working in a collaborative setting preparing us for on the job application of database management.
