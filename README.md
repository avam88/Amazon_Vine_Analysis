# Amazon Product Review Vine Program Analysis
## Introduction of Compensated Reviews and Exposure to Bias
Analysis of the Amazon Vine Review Program - Service platform provided by Amazon to Vendors/Manufacturers/publishers that allows access to amazon consumer base as candidates to participate in providing reviews. Some reviewers are compensated for their participation and others are not. Amazon and participating vendors want analysis performed on the review data to determine if offering payment for reviews introduces bias into the review process, skewing the data. 

## ETL Pipeline
To perform analysis on the dataset and push the data through the ETL pipeline, raw dataset was loaded into google colab. Using Pyspark to transform the data in dataframe and perform preliminary filtering and consolidating. Dataframe were loaded into pgAdmin and transformed into csv. From there csv were loaded into jupyter notebook to use python to perform statistical analysis on.

## Results
To determine if compensated reviews contain bias, we needed first to filter from the dataset the total number of reviews provided in the dataset that were gathered as part of the vine program (paid reviews) versus those that were not (unpaid). From the filtered dataset to further determine of the vine program reviews how many were 5 star, versus how many 

- Paid Reviews vs Unpaid Reviews (Vine vs Normal)
  - 49 vs 151,400
- Total 5 Star Paid vs Unpaid Reviews
  - 9 vs 78,061
- %5 Star Paid vs Unpaid Reviews
  - 18.4% vs 51.6%

Evidence that there is dissimilar, deviant form each other. skew in the dataset, however reviews generated from participants in the vine program who were compensated for their review were LESS likely to provide a 5 star review. We can see that the introduction of compensation has a negative impact bias on the performance of a product 

To capture the, perform the same summary analysis across all point star reviews to reveal if the vine program data tends to still skew toward 4 star, while unpaid might be more evently dispersed. While we don't see an inflated amount of 5 star, perhaps there are more 4 star

Compare the analysis of paid versus unpaid for this product against that of other products. Do not want to illustrate the outlier in the product.
