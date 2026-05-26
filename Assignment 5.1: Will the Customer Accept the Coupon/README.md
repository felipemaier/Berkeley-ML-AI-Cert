# Assignment 5.1: Will the Customer Accept the Coupon?

## Overview

The goal of this project is to analyze a UCI Machine Learning dataset that comes from a survey conducted by Amazon 
Mechanical Turk. This survey asks a person whether he will drive to a restaurant or coffee shop, and then asks the 
person whether he will accept a coupon.

The final goal of this project, after analyzing the data, is to highlight the differences between drivers who accept 
and reject coupons.

## Procedure

To achieve the goal, we performed a technical analysis on a Jupyter Notebook. From a high level 
the steps were:

1. Prepare the tooling and load the dataset
2. Explore the data to understand the characteristics of the dataset
3. Look for duplicates, missing values and handle them appropriately
4. Perform exploratory data analysis to understand the data
5. Perform data visualization to understand the data

## Results

### Overall Coupon Acceptance Rate

After cleaning the data, we analyzed the Overall Coupon Acceptance Rate, or in other words,
the percentage of customers who accept the coupon, this is shown in the following graph:

![Coupon Acceptance Rate — Overall](images/CouponAcceptanceRate.png)

Near 60% of the customers accepted the coupon.

### Coupon Types

![Coupon Types](images/CouponDistribution.png)

The most common coupon type are "Coffee House" (32%) and "Restaurant with average expense less than $20 per person" (22%).

### Acceptance per Coupon Type

![Acceptance per Coupon Type](images/AcceptanceByCouponType.png)

The 2 groups that have the highest acceptance rate are "Carry out & Take away" (73%) and "Restaurant with average 
expense less than $20 per person" (71%).

### Segments of Acceptance Across All Coupons

If we analyze each coupon type individually, we can see that the characteristics of each coupon type are different.

#### Coffee House

|  | feature | value | acceptance\_rate | n |
| :--- | :--- | :--- | :--- | :--- |
| 53 | occupation | Healthcare Practitioners & Technical | 76.056338 | 71 |
| 45 | occupation | Building & Grounds Cleaning & Maintenance | 72.727273 | 11 |
| 83 | CoffeeHouse | 4\~8 | 68.244576 | 507 |
| 29 | age | below21 | 67.832168 | 143 |
| 84 | CoffeeHouse | gt8 | 65.789474 | 342 |

### Carry out & Take away

|  | feature | value | acceptance\_rate | n |
| :--- | :--- | :--- | :--- | :--- |
| 45 | occupation | Building & Grounds Cleaning & Maintenance | 100.000000 | 9 |
| 62 | occupation | Protective Service | 96.666667 | 30 |
| 49 | occupation | Construction & Extraction | 96.428571 | 28 |
| 41 | education | Some High School | 93.750000 | 16 |
| 53 | occupation | Healthcare Practitioners & Technical | 92.500000 | 40 |

### Restaurant(<20)

|  | feature | value | acceptance\_rate | n |
| :--- | :--- | :--- | :--- | :--- |
| 62 | occupation | Protective Service | 89.473684 | 38 |
| 49 | occupation | Construction & Extraction | 88.571429 | 35 |
| 18 | expiration | 1d | 83.553142 | 1289 |
| 57 | occupation | Life Physical Social Science | 83.333333 | 36 |
| 16 | time | 6PM | 82.657343 | 715 |

### Restaurant(20-50)

|  | feature | value | acceptance\_rate | n |
| :--- | :--- | :--- | :--- | :--- |
| 61 | occupation | Production Occupations | 72.727273 | 11 |
| 99 | Restaurant20To50 | gt8 | 68.750000 | 32 |
| 54 | occupation | Healthcare Support | 65.625000 | 32 |
| 98 | Restaurant20To50 | 4\~8 | 63.095238 | 84 |
| 6 | passanger | Partner | 62.500000 | 136 |

### Bar

|  | feature | value | acceptance\_rate | n |
| :--- | :--- | :--- | :--- | :--- |
| 41 | education | Some High School | 78.571429 | 14 |
| 78 | Bar | 4\~8 | 77.551020 | 147 |
| 79 | Bar | gt8 | 71.739130 | 46 |
| 61 | occupation | Production Occupations | 68.750000 | 16 |
| 43 | occupation | Architecture & Engineering | 66.666667 | 27 |

## Top 10 Acceptance Segments Across All Coupons

Merged together, and after removing small segments that are not significant,
we can see that the top 10 acceptance segments across all coupons are:

|  | feature | value | acceptance\_rate | n | coupon |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 15 | time | 2PM | 86.602871 | 209 | Carry out & Take away |
| 18 | expiration | 1d | 83.553142 | 1289 | Restaurant\(&lt;20\) |
| 37 | education | Associates degree | 83.248731 | 197 | Carry out & Take away |
| 16 | time | 6PM | 82.657343 | 715 | Restaurant\(&lt;20\) |
| 16 | time | 6PM | 81.995134 | 411 | Carry out & Take away |
| 15 | time | 2PM | 81.487102 | 659 | Restaurant\(&lt;20\) |
| 4 | passanger | Friend\(s\) | 80.354880 | 789 | Restaurant\(&lt;20\) |
| 64 | occupation | Sales & Related | 79.828326 | 233 | Restaurant\(&lt;20\) |
| 1 | destination | No Urgent Place | 79.458795 | 1626 | Restaurant\(&lt;20\) |
| 0 | destination | Home | 79.126214 | 618 | Carry out & Take away |

![Top10AcceptanceSegmentsAcrossAllCoupons](images/Top10AcceptanceSegmentsAcrossAllCoupons.png)

# Conclusion

As expected, drivers are more likely to accept coupons for food (Restaurant <$20 and Carry out) around lunch 
(2PM) and dinner (6PM), where acceptance rates are near 80%.

For Bar coupons specifically, the deeper analysis showed that drivers who are already regular customers are more 
likely to accept them, but even then, the acceptance rate is still below Restaurant coupons at lunch or dinner.









