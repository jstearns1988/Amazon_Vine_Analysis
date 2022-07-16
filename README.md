# Amazon_Vine_Analysis

## Overview of the Analysis

The purpose of this analysis was to conduct a meta-analysis of Amazon reviews produced as part of the Amazon Vine program. The Amazon Vine program works by having select, compensated members of Amazon's community of reviewers rate sample products. The data of this project was analyzed to determine if any bias exists toward favorable reviews from the paid Vine members.

### I chose a dataset from the Toys product category.

To begin the analysis, I created a database with Amazon RDS and connected the server in pgAdmin. I ran a query in pgAdmin to create the customers_table, products_table, review_id_table, and vine_table.

I then used Google Colab Notebook to extract the Toys dataset and created a new dataframe.
![Toys DF](https://github.com/jstearns1988/Amazon_Vine_Analysis/blob/main/Resources/Toys%20DF.png?raw=true)

The Toys DataFrame was then transformed into four separate DataFrames to match the schema in the pgAdmin tables.

### customers_table DataFrame
![customers_table DataFrame](https://github.com/jstearns1988/Amazon_Vine_Analysis/blob/main/Resources/customer%20table%20df.png?raw=true)

### products_table DataFrame
![products_table DataFrame](https://github.com/jstearns1988/Amazon_Vine_Analysis/blob/main/Resources/products%20table%20df.png?raw=true)

### review_id DataFrame
![review_id DataFrame](https://github.com/jstearns1988/Amazon_Vine_Analysis/blob/main/Resources/review%20id%20df.png?raw=true)

### vine_table DataFrame
![vine_table DataFrame](https://github.com/jstearns1988/Amazon_Vine_Analysis/blob/main/Resources/vine%20table%20df.png?raw=true)


## Results

Using PySpark I created new DataFrames to retrieve all rows where the total_votes count is equal to or greater than 20, all rows where the number of helpful_votes divided by total_votes is equal to or greater than 50%, all rows where a review was written as part of the Vine program (paid), all rows where a review was written as part of the Vine program (unpaid), and a final DataFrame analyzing numbers and percentaged of 5-star reviews.

### All rows where the total_votes count is equal to or greater than 20

![Greater than 20](https://github.com/jstearns1988/Amazon_Vine_Analysis/blob/main/Resources/greater%20than%2020.png?raw=true)

### All rows where the number of helpful_votes divided by total_votes is equal to or greater than 50%

![Greater than 50](https://github.com/jstearns1988/Amazon_Vine_Analysis/blob/main/Resources/greater%20than%2050%20percent.png?raw=true)

### All rows where a review was written as part of the Vine Program (paid)

![Paid](https://github.com/jstearns1988/Amazon_Vine_Analysis/blob/main/Resources/vine%20paid.png?raw=true)

### All rows where a review was written as part of the Vine Program (unpaid)

![Unpaid](https://github.com/jstearns1988/Amazon_Vine_Analysis/blob/main/Resources/Vine%20unpaid.png?raw=true)

### A final DataFrame analyzing numbers and percentaged of 5-star reviews

![All 5 Star](https://github.com/jstearns1988/Amazon_Vine_Analysis/blob/main/Resources/Reviews%20DF.png?raw=true)

### How many Vine reviews and non-Vine reviews were there

There were a total of 1266 Vine reviews and 62,028 non-Vine reviews.

### How many Vine and non-Vine reviews were 5 stars

There were 432 5-star Vine reviews and 29,982 non-Vine 5-star reviews.

### What percentage of Vine and non-Vine reviews were 5 stars

There were approximately 34% 5-star Vine reviews and 48% non-Vine 5-star reviews.

## Summary

Viewing the results of this analysis, it can be determined there is not a strong bias toward five-star reviews from paid Amazon Vine reviewers. According to the dataframes created, there may be a slight trend in Vine reviewers to be more critical in there reviews when you view the higher percentage of 5-star reviews for the non-Vine reviewers in the DataFrame above.

To further analyze the theory that Vine reviewers are NOT skewing their reviews based on their paid status, an analysis on the negative review data from paid and unpaid reviewers should be analyzed. In fact, a review of all star reviews should be compared between the two groups. It would be helpful to review more than just the Toys dataset. Are these results similar to all categories, some, or none?
