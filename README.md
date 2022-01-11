# Amazon_Vine_Analysis
## Overview
In this project I used US Apparel product reviews from Amazon. The goal was to analyze if it would be worth it to subscribe to a Vine program if we were to sell similar products through their platform. The vine review program is an incentive model in which customers are gifted free stuff when they write good reviews. I was able to use PySpark to extract, transform, and load (ETL) the data to a AWS RDS I created and connected to my PostgreSQL server to be able to query it and extract my finished tables from there. Part of the data transformation was made using pandas as well.

The objective of this project was to familiarize myself with Spark. Apache Spark is a unified analytics engine for large-sacale data processing. This means that when working with big data, Spark is one of the best technologies out there to use because of its in-memory computation instead of disk-based solution. It allows for lazy evaluation and delaying expressions or commands until its needed.
## Roadmap
The first step was to extract the dataset from an AWS S3 using PySpark in order to transform it and load it to AWS again. Please refer to Amazon_Reviews_ETL.ipynb to see the code. Note that I downloaded it as a jupyter notebook file, but it was originally created in Google Colab for PySpark to run. There, I basically divided the whole dataframe into 4 smaller dataframes for better analysis. These dataframes were then loaded to AWS RDS using a a connection from PySpark to PostgreSQL.
## Extract and Transform the data
![1](https://user-images.githubusercontent.com/90945875/149027536-3c724a23-2a56-48ce-ba13-d5c822302fe2.PNG)

![2](https://user-images.githubusercontent.com/90945875/149027791-9a6785bf-27a8-45a0-8626-3c4ae65a7e8b.PNG)

![3](https://user-images.githubusercontent.com/90945875/149027962-a79506b8-1cba-48f1-8487-200253a0ca0a.PNG)

![4](https://user-images.githubusercontent.com/90945875/149028097-dae4c804-2d2b-4278-ac45-635f563f7ef0.PNG)
## Loading the data
![vine](https://user-images.githubusercontent.com/90945875/149028585-fe80217c-f930-4f69-bf3f-d4b0cdfdc716.PNG)

![review](https://user-images.githubusercontent.com/90945875/149028951-e6a38446-4510-4eb4-a8e1-f2b902e96483.PNG)

![products](https://user-images.githubusercontent.com/90945875/149029157-1eafcabc-6f32-4b96-a602-44858da869cd.PNG)

![customers](https://user-images.githubusercontent.com/90945875/149029332-dedfa12d-2d5d-4a48-8ce3-19eff75a73d4.PNG)
## Result
we worked with the last table called vine_table to perform the Vine program analysis to filter the best reviews, and see if there were significantly more 5-star reviews in the paid and incentivized (vine) program. The best reviews were those that were highly voted as helpful. Then, I filtered to see which of those were part of the vine program and which were not. Please refer to the Amazon_Vine_Analysis.ipynb


* Vine (paid) Reviews
* 94 total reviews
* 48 were 5 star reviews
* 51% of vine (paid) reviews were 5 star
* Unpaid Reviews
* 40,471 total reviews
* 15663 5 star reviews
* 38.7% of unpaid reviews were 5 star

## Summary
In conclusion, the vine program might just not be worth it for the apparel category. As it can be seen, there were not many helpful reviews that made part of it (total of 94), and only around half of them were 5-star rated (51%). Very similarly to the unpaid reviews which also only less than a half of them were 5 star rated (38%). Even though the percentages may be misleading as the volume of reviews in the vine and non-vine programs vary so much, this itself is a sign that the vine program is not very popular in this category. We might not want to pay for it as it is not incentivizing the people to write better reviews.

![further](https://user-images.githubusercontent.com/90945875/149030687-2193768b-8226-4315-b01f-64d081711d5f.PNG)





