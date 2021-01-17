# Amazon_Vine_Analysis

## Overview of the analysis
The main purpose of this analysis is to analyze trends in Amazon reviews and see if there is a difference between review results between paid and unpaid reviews. This review data set from Amazon was from video game reviews. I unfortunately had to stop my program loading data into PostGres after giving it nearly 30 minutes to process, so my numbers may appear small because of this.

## Results

There were 94 out of 40,471 vine reviews left on video games that had greater than 20 reviews total left. 

```
totalpaidreviews = df_paid["review_id"].count()
totalpaid5starreviews = df_paid[df_paid["star_rating"] == 5.0]
totalpaid5starreviews = totalpaid5starreviews["review_id"].count()
print("Total Paid Reviews = ", totalpaidreviews)
print("Total Paid 5 Star Reviews = ", totalpaid5starreviews)

percenttotalpaid5starreviews = (totalpaid5starreviews/totalpaidreviews)
print("Percent Total Paid 5 Star Reviews = ", percenttotalpaid5starreviews*100, "%")

print ("")

totalunpaidreviews = df_unpaid["review_id"].count()
totalunpaid5starreviews = df_unpaid[df_unpaid["star_rating"] == 5.0]
totalunpaid5starreviews = totalunpaid5starreviews["review_id"].count()
print("Total Unpaid Reviews = ", totalunpaidreviews)
print("Total Unpaid 5 Star Reviews = ", totalunpaid5starreviews)

percenttotalunpaid5starreviews = (totalunpaid5starreviews/totalunpaidreviews)
print("Percent Unpaid Paid 5 Star Reviews = ", percenttotalunpaid5starreviews*100, "%")

```
Total Paid Reviews =  94
Total Paid 5 Star Reviews =  48
Percent Total Paid 5 Star Reviews =  51.06382978723404 %

Total Unpaid Reviews =  40471
Total Unpaid 5 Star Reviews =  15663
Percent Unpaid Paid 5 Star Reviews =  38.701786464381904 %


## Summary

There is definite positivity bias in the Vine reviews, as the percentage of five star ratings is much higher. However, the percentage of Vine reviews out of the total number of reviews make me feel that the impact is negligible. 

Rather than a percentage of five star reviews out of the total review count, it may be more beneficial to weight the whole of the reviews. While a larger number of paid reviews may have given five stars, the remainder may have actually given lower ratings. It would be helpful to see the average rating per reviewer for Vine and non-Vine ratings. 
