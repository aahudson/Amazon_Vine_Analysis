# Amazon_Vine_Analysis
# Overivew 
The purpose of this project was to analyze Amazon reviews written by members of the paid Amazon Vine program. One of the fifty datasets were 
chosen to review from https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt. 
## Actions Performed 
Used AWS Command Line Interface to copy Amazon reviews dataset https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Digital_Ebook_Purchase_v1_01.tsv.gz into my Amazon S3 Bucket.
Colab was used to created the following DataFrames
- df (containing all the data from the select Amazon Reviews)
- customers_df (containing coustomer_id and customer_count)
- products_df (containing product_id and product_title with dropped duplicates)
- review_id_df (containing review_id, customer_id, product_id, product_parent, and review_date. Also note that the review_date column was converted to a date datatype)
- vine_df (containg review_id, star_straing, helpful_votes, total_votes, vine, and verified_purchase)
Next pgAdmin was used to create four tables:
- review_id_table
- produts_table
- customers_table
- vine_table
Then Colab was used to connect the AWS RDS instance and write each DataFrame to its table. 
# Determine Bias of Vine Reviews 
Next the bias towards reviews were identified in the Vine Reviews. 
- Data was filtered to create a new DataFRame  to retrieve all the rows where the total_votes count is equal to or greater than 20 to pick reviews that are more likely to be helpful and to avoid having division by zero errors later on.
- The DataFrame was then used to retrieve all the rows where the number of helpful_votes divided by total_votes is equal to or greater than 50%.
- Next it was filtered to etrieves all the rows where a review was written as part of the Vine program (paid), vine == 'Y'.
- All the rows where the review was not part of the Vine program (unpaid), vine == 'N' were also retrived. 
- Lastly  the total number of reviews, the number of 5-star reviews, and the percentage of 5-star reviews for the two types of review (paid vs unpaid).
# Summary 
Based on the results, it appears that there is a positivity bias for reviews in the Vine program. 
An additional analysis that could be done with the dataset to support this statement is to compare the average star rating for Vine reviews and non-Vine reviews. This would provide further insight into the impact of the Vine program on product ratings.
