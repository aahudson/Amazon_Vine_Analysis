# Amazon_Vine_Analysis
The purpose of this project was to analyze Amazon reviews written by members of the paid Amazon Vine program. One of the fifty datasets were 
chosen to review. 
# Actions Performed 
Used AWS Command Line Interface to copy Amazon reviews dataset https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Digital_Ebook_Purchase_v1_01.tsv.gz into my Amazon S3 Bucket.
Colab was used to created the following DataFrames
- df (containing all the data from the select Amazon Reviews)
- customers_df (containing coustomer_id and customer_count)
- products_df (containing product_id and product_title with dropped duplicates)
- review_id_df (containing review_id, customer_id, product_id, product_parent, and review_date. Also note that the review_date column was converted to a date datatype)
- vine_df (containg review_id, star_straing, helpful_votes, total_votes, vine, and verified_purchase)

