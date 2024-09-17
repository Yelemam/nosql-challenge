# nosql-challenge

![London](https://github.com/user-attachments/assets/976f198c-4ca1-4d59-b7b5-05f6f2973c29)


# NoSQL Challenge - UK Food Standards Agency Database Analysis
#Project Description

  This project is part of the Module 12 Challenge, which involves analyzing UK Food Standards Agency data to assist the food magazine Eat Safe Love in      
  determining which establishments to feature in their articles. The project focuses on setting up a NoSQL MongoDB database, updating the database with new data,
  and performing exploratory data analysis using PyMongo.re articles.
   
# Installation and Setup
# Prerequisites

   Ensure that the following are installed on your machine:
   * MongoDB
   * Python 3.x
   * Jupyter Notebook
   * Python libraries:
     * pymongo
     * pandas
     
# Part 1: Database and Jupyter Notebook Set Up

  1. Database Import:
     * The MongoDB database is set up using the following mongoimport command: This imports the dataset into a MongoDB collection called establishments 
       under the uk_food database.
    
        mongoimport --db uk_food --collection establishments
         --file establishments.json --jsonArray --drop 
         
  2. PyMongo Setup:
     * The Jupyter notebook sets up the environment by importing necessary libraries, including pymongo and pprint: 
     
        from pymongo import MongoClient
        from pprint import pprint  
        
    * An instance of the Mongo client is created, and the uk_food database is assigned to variable:  mongo = MongoClient(port=27017)
        db = mongo['uk_food'] 
        
  3. Data Verification:
    * The notebook verifies the import by listing the databases and collections in MongoDB:
    
       mongo.list_database_names()  
       db.list_collection_names() 

     
# Part 2: Update the Database

   1. Insert a New Restaurant:
      * The new restaurant "Penang Flavours" is added to the establishments collection in the database. This restaurant is located in Greenwich but hasn't 
        been rated yet. 
    
   2. Update BusinessTypeID:
      * A query is performed to find the BusinessTypeID for "Restaurant/Cafe/Canteen", and the new restaurant’s record is updated   
     
   3. Remove Establishments in Dover:
      * All establishments in the Dover Local Authority are removed
     
   4. Convert Data Types:
      * Use the update_many() function to convert latitude and longitude fields from strings to decimal numbers, and RatingValue to integers
     
# Part 3: Exploratory Analysis

   1. Perform the following exploratory data analysis to answer questions posed by Eat Safe Love:
      * Establishments with a Hygiene Score of 20:

   2. London Establishments with a Rating Value ≥ 4:
      * Query to find establishments in London with a RatingValue greater than or equal to 4
      
   3. Top 5 Establishments near Penang Flavours:
      * Find the top 5 establishments near "Penang Flavours" with a RatingValue of 5 and the lowest hygiene score
     
   4. Local Authorities with the Most Hygiene Scores of 0:
      * Perform an aggregation to find Local Authorities with the most establishments scoring 0 in hygiene
     
# Results and Findings
   The analysis helps identify establishments with poor hygiene scores, highly rated establishments in London, and top establishments near "Penang Flavours".
   These insights can be used by Eat Safe Love magazine to focus future articles on notable establishments.

# Table of Content
1. NoSQL_setup_starter.ipynb: jupyter notebook
2. NoSQL_analysis_starter.ipynb: jupyter notebook
3. aggregate_df.csv : Saved csv file DataFrame output
4. hygiene_df.csv: Saved csv file DataFrame output
5. london_rating.csv: Saved csv file DataFrame output
6. near_penang_df.csv: Saved csv file DataFrame output
7. London.png: image for london
