# Amazon's Vine Product Review Program :
## An Analysis of Potential Bias in Compensated Reviews
The Amazon Vine Review Program is a service offered by Amazon to vendors, manufacturers and publishers that makes Amazon's vast consumer base accessible to participating businesses for paid product reviews. Vendors participating in the program need to establish if reviews generated through the vine program are biased by the introduction of compensation.

## ETL Pipeline
To establish if paid reviews introduce bias in a dataset, we will perform analysis on a series of reviews for DVD/Video products generated through the vine program and compare them to reviews generated voluntarily where consumers were not compensated. In order to perform analysis, the raw dataset needed to be pushed through the ETL pipeline (extracted, filtered and transformed) in the following way :
- The raw dataset provided by Amazon was loaded into a google colab notebook where preliminary filtering and consolidating of data and tables was performed using methods and functions from the Pyspark library. See TABLE1 for example.
- The pre-filtered dataframes of consumer data for paid and unpaid reviews were then loaded into our database program (pgAdmin) and exported into csv format for further analysis. 
- Lastly the csv files were loaded into a jupyter notebook as dataframes in order to use python functions to perform the final statistical analysis. See TABLE2 for example.

![Screen Shot 2022-10-03 at 9 55 19 PM](https://user-images.githubusercontent.com/107326987/193963631-86f48b7c-8296-4ef6-baae-59964792fd09.png)

TABLE1 : filtered pyspark dataframe for all reviews generated outside of Vine program

![Screen Shot 2022-10-03 at 9 48 01 PM](https://user-images.githubusercontent.com/107326987/193963625-77783831-c44d-4fcc-8480-f6242d2f1c10.png)

TABLE2 : filtered pandas dataframe showing final dataset ready for statistical analysis

## Results
To determine if compensated reviews contain bias, we will parse out a series of baseline statistics for paid versus unpaid reviews. Our determination of bias will ultimately be a study on the overall occurance of 5 star reviews in proportion to total reviews.

- Total Reviews : Paid vs Unpaid (Vine vs Normal)
  - From our original dataset there were 49 total Vine/Paid reviews and 151,400 unpaid reviews
- Total 5Star Reviews : Paid vs Unpaid
  - From our original dataset there are a total of 9 5star Paid reviews and 78,061 unpaid reviews
- Total % 5Star Reviews : Paid vs Unpaid
  - A total of 18.4% of paid reviews were 5star and a total of 51.6% of unpaid reviews were 5star

The final statistics for paid and unpaid reviews are very dissimilar. The introduction of compensation clearly has influence on the review as the final analysis shows deviance in the datasets. We can see that reviews generated from participants in the vine program who were compensated for their review were LESS likely to provide a 5 star review - almost 3 times less likely. We can see that the introduction of compensation has a negative impact bias on the review performance of a product in the DVD/Video category. 

## Further Analysis : Understanding our Results in a Larger Context
This is a fairly small dataset to perform analysis on (with only 49 total paid reviews). If we wanted to draw conclusions about the Vine Program and in general about the impact of compensation on review status, further analysis would need to be performed on datasets of other product categories from Amazon's database. In addition to repeating this analysis on review data from other product categories, further analysis would also need to be performed across the entire review score range. A visual mapping or scatter plot of where the entire range of reviews (1 through 5) fall for paid versus unpaid reviews would tell us more about the ultimate skew of each dataset. 
