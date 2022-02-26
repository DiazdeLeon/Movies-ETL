# 1. Objectives of the ETL challnege

The main purpose of the challenge was to refactor the code from this module to create one function that takes in the three files: Wikipedia data, Kaggle metadata, and the MovieLens rating data, and performs the ETL process by adding the data to a PostgreSQL database. Also, is important to underline the full comprehension of the ETL process. 

# 2.	ETL Process
Extract, Transform, Load also known as ETL is a data integration process that combines data from multiple data sources into a single, consistent data store that is loaded into a data warehouse or other target system. ETL cleanses and organizes data in a way which allows to perform a better and more accurate analysis.
 
![image](https://user-images.githubusercontent.com/95872614/155825130-67acada5-b3b2-42fe-8d10-cd6ae04559b7.png)

During the extract step, raw data is copied or exported from source locations to a staging area. The data may come from several data sources. 
During transform, the raw data undergoes data processing. Here, the data is transformed and consolidated for its intended analytical use case. This phase can involve the following tasks:

-	Filtering, cleansing, de-duplicating, validating, and authenticating the data.
-	Performing calculations, translations, or summarizations based on the raw data. This can  include changing row and column headers for consistency, converting currencies or other units of measurement, editing text strings, and more.
-	Conducting audits to ensure data quality and compliance
-	Removing, encrypting, or protecting data governed by industry or governmental regulators
-	Formatting the data into tables or joined tables to match the schema of the target data warehouse.

During loading, which is the last step, the transformed data is moved from the staging area into a target data warehouse. Afterwards, the user may use the data for his/her own convenience with the certainty that the data is clean and consistent. 

# 3.	Refactoring the code.
The first step was to write a function that reads in the three data files and creates three separate DataFrames (Wikipedia data, Kaggle metadata, and MovieLens rating data).
 
![image](https://user-images.githubusercontent.com/95872614/155825171-d619f4fd-d75b-4403-b00a-c5cdd45747b7.png)

The second step was to transform the Wikipedia data and merge it with the Kaggle metadata. While extracting the IMDb IDs and dropping duplicates, followed by a try-except block to catch errors.
 
![image](https://user-images.githubusercontent.com/95872614/155825144-5be0ba44-b21e-48b0-994d-a2928b024184.png)

The third part was to transform the Kaggle metadata and MovieLens rating data, then convert the transformed data into separate DataFrames. Afterwards, it was merged the Kaggle metadata DataFrame with the Wikipedia movies DataFrame to create a new DataFrame. Finally, it was merged the MovieLens rating data DataFrame with the movies_df DataFrame to create the movies_with_ratings_df.
 
![image](https://user-images.githubusercontent.com/95872614/155825150-d2c8e648-4387-48ac-bb7b-79774c05aada.png)

Finally, the last step was to load the movies_df DataFrame and MovieLens rating CSV data to a SQL database. Here is presented the queries from PGAdmin.

![image](https://user-images.githubusercontent.com/95872614/155827374-66382b30-00a4-485e-9bb6-989f6f8a71fd.png)


 

