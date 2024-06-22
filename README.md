# Ford-Secondary-Vehicles-Analysis
## Executive Summary
This report delves into the analysis of a comprehensive dataset encompassing 17,966 used Ford
 vehicle listings originating from an unspecified country within the Balkan region. The primary
 objective of this analysis is to decipher the underlying factors that exert a significant influence on the
 pricing of Ford vehicles in the secondary market. This valuable information can empower Ford and
 associated dealerships to strategically tailor their marketing campaigns and pricing strategies to
 maximize sales and revenue. Through a combination of descriptive statistics, k-means clustering
 incorporating PC analysis, association rules, multiple linear regression, k-nearest neighbors testing,
 and regression tree modeling, the analysis unravels the intricate relationships between various vehicle
 characteristics and their corresponding market prices. Notably, manual transmissions emerge as a
 cost-effective choice for buyers, commanding lower prices compared to their automatic counterparts,
 signaling a consumer preference for the latter.
 Furthermore, the analysis reveals a pricing distinction between petrol and hybrid vehicles, with petrol
 models generally being more affordable and hybrids demanding a premium price, reflective of the
 growing appeal of eco-friendly options in the market. Multi-purpose vehicles (MPVs) are positioned
 at a lower price point, while convertibles carry higher price tags, attributed to their perceived
 exclusivity and heightened appeal. with each increase in the model year of the vehicle, there is a
 corresponding rise in the price by $1,127.95, indicative of advancements in technology and the
 perceived value associated with newer models. Finally, the analysis highlights a consistent pattern,
 indicating that with each additional mile on a vehicle's odometer, there is an estimated decrease of
 $0.064 in its market value, holding all other factors constant.
 
## Introduction
 The used car market stands as a significant pillar of the global automotive industry, accounting for a
 substantial portion of overall vehicle sales. Understanding the intricate dynamics that influence the
 pricing of used cars is crucial for both manufacturers and dealerships. This report addresses this
 critical need by conducting an in-depth analysis of a dataset of used Ford vehicle listings originating
 from a South East European country. This pursuit is not merely academic; it is a strategic initiative
 aimed at providing stakeholders with actionable insights to refine marketing strategies, pricing
 structures, and overall market positioning.

 ## Data
  Sourced from Kaggle, the dataset comprises 17,966 data points, each representing a used Ford
 vehicle. Featuring 9 columns encompassing variables such as price, model, year, mileage, fuel type,
 tax, mpg, and engine size, it serves as the foundation for an in-depth analysis of factors influencing
 pricing. Challenges encountered during the analysis included the exclusion of the tax column due to
 variable tax rates dependent on location. Additionally, the dataset lacked sales and revenue figures,
 limiting the scope of financial insights. Another obstacle pertained to the dataset's temporal
 aspects—being outdated by 3 years and containing an implausible data point from the year 2060. To
 address the complexities of the dataset, we undertook the task of grouping certain data and
 implementing dummy coding. Despite these limitations, the dataset remains a valuable resource
 offering insights into market trends, transmission preferences, and correlations between pricing and
 various vehicle features.

 ## Analysis
 ### Descriptive Statistics
 We started by utilizing a set of methods to summarize and describe the main features of the dataset,
 such as its central tendency, variability, and distribution. We used the summary function on all the
 variables to find basic descriptive information as illustrated below. The examination of the dataset
 reveals pertinent information regarding Ford’s vehicles in the used automotive market. The average
 price of the observed cars is approximately $12,280, exhibiting a price range spanning $54,500.
 Notably, there exists a vehicle in the secondary market with an exceptionally low mileage of only 1
 mile, contributing to an average mileage of around 23,363 miles, with a broad range extending to
 177,643 miles. The average fuel efficiency stands at 57.91 miles per gallon, demonstrating a range of
 approximately 181, which can be attributed to the inclusion of hybrid cars that seamlessly transition
 between electric and gas modes. Furthermore, the average engine size within the dataset is 1.35, with
 5 representing the largest and 0 the smallest. The presence of zero engine size may be elucidated by
 the prevalence of electric cars utilizing batteries instead of traditional engines. Additionally, variables
 such as model, transmission, and fuel type, initially characterized as character types, have been
 converted into numeric variables to facilitate predictive analysis.

 ![image](https://github.com/SarthakJN99/Ford-Secondary-Vehicles-Analysis-/assets/144856781/c70fcd64-7416-419a-b13d-08be7af27736)

 The dataset comprises 24 distinct car models, with Fiesta, Focus, and Kuga being the most prevalent,
 in that sequence. Notably, Fiesta and Focus are available in compact hatchback and sedan forms,
 while Kuga is a compact crossover SUV, indicating a prevalence of smaller vehicles in the secondary
 market.

 ![image](https://github.com/SarthakJN99/Ford-Secondary-Vehicles-Analysis-/assets/144856781/2101bb47-24a3-4369-af2e-aeb7141bbb9b)

 The dataset comprises five fuel types: Diesel, Petrol, Electric, Other, and Hybrid. Among them, 5,762
 cars run on Diesel, 12,179 on Petrol, and 22 are Hybrid. Plot 2 illustrates this. Contrarily there are
 three types of transmissions- Manual, Automatic, and Semi-Auto with Manual making a bulk of the
 total with 15,518 units as seen in Plot 3.

 ![image](https://github.com/SarthakJN99/Ford-Secondary-Vehicles-Analysis-/assets/144856781/4ea616b4-3c54-47b5-b895-65f0cddf7cdb)

 Plot 4 displays the frequency distribution of vehicle entries by year (1996-2020) in the dataset. Most
 entries fall within the years 2013-2019, with a notable peak in 2017, and a sharp fall in 2020, while
 years before 2005 have fewer occurrences.

### K-Means Clustering

![image](https://github.com/SarthakJN99/Ford-Secondary-Vehicles-Analysis-/assets/144856781/5107529c-2a37-4479-9dc0-8f83ee642192)

After experimenting with various values of K, it was observed that the most effective visualization plot was obtained with K=8. The
 resulting output revealed eight centroids, each characterized by values corresponding to the variables of interest: year, price, mileage, mpg, and
 engineSize. These centroids represent the average values of the data points within each cluster. However, despite choosing K=8, it became
 apparent that the cluster plot (See Plot 5) generated was not as informative or helpful as expected. The centroids provided an average
 representation, yet the clusters did not offer a clear and distinct separation in the visualization. For instance, the green cluster (Cluster 3) has two sets of data points that are very far from each other
 but are still being visualized in the same set, despite experimenting with different values of K. This anomaly might be expounded by the fact that Dim 1
 explains 46.4% of the cluster plot as opposed to only 29.6% of Dim 2. We also calculated the cluster sizes of each of these 8 clusters. However, to gain a
 more in-depth understanding, a Principal Component Analysis (PCA) was conducted on the data.

 ![image](https://github.com/SarthakJN99/Ford-Secondary-Vehicles-Analysis-/assets/144856781/2894ca47-e95d-42c9-8988-6f4ba64977db)
 ![image](https://github.com/SarthakJN99/Ford-Secondary-Vehicles-Analysis-/assets/144856781/e73ac956-620d-4732-b003-7b785d411924)
 ![image](https://github.com/SarthakJN99/Ford-Secondary-Vehicles-Analysis-/assets/144856781/0941cf59-8ed3-450f-91ae-474a9a5bd167)

  In the context of a PCA on variables related to cars (year, price, mileage, mpg, engineSize), the correlation matrix for the first two principal components, Dim.1 and Dim.2, provides
 valuable insights into the relationships between the original variables and these principal components.
 Dim.1 exhibits a strong positive correlation with year and price, suggesting that higher values in these
 variables contribute significantly to the first principal component. Conversely, mileage has a strong
 negative correlation with Dim.1, indicating that lower mileage is associated with higher values of
 Dim.1. Turning to Dim.2, engineSize shows a strong positive correlation, while mpg demonstrates a
 moderately negative correlation. An intuitive explanation of this is that on a cluster plot with Dim 1 on
 the x-axis and Dim 2 on the y-axis, the cluster on the upper right-hand side of the plot would consist
 of pricier cars, probably have stronger engines and have comparatively less mileage on them, and vice
 versa.

 ![image](https://github.com/SarthakJN99/Ford-Secondary-Vehicles-Analysis-/assets/144856781/404565b7-3163-4882-a333-095bae13ce12)

 ### Association Rules

 Another method that we used is association rules, which helps to find out the relationships between
 the factors and the price as well as themselves together. The variables- Fuel Type, Transmission, Year,
 Engine Size, Mileage, and Price, were dummy-coded.
 Fuel type was encoded as 1 for "Petrol" and 0 for other types, given the prevalence of petrol in most
 cars. Transmission was represented as 1 for "Manual" and 0 for other types, reflecting the 86%
 predominance of manual transmission. For Year, values after 2010 were coded as 1, with other years
 coded as 0. Engine size was coded as 1 for sizes ≥1.6 and 0 for sizes <1.6. Mileage was set to 1 for
 values ≥23362.60876 and 0 for smaller values. Similarly, the Price was coded as 1 for values
 ≥12279.53484 and 0 for smaller values. We ran the association code with support of 0.05 and
 confidence of 0.7 and generated the output below. Unfortunately, there were no results of “price” on
 the RHS, which indicates that there were no dominant variables that straightforwardly highly
 influenced the price from this method. Car prices are a complex combination of variables, which
 needs other methods to analyze the data.

 ![image](https://github.com/SarthakJN99/Ford-Secondary-Vehicles-Analysis-/assets/144856781/9070eb3d-1741-4abe-8583-82407c03bf5f)

However, on the other hand, we found some noticeable insights that are valuable for car dealers and
 manufacturers. Rules 1, 13, and 14 show a strong correlation between higher prices, higher mileage,
 and larger engine size. Rule 1 shows that a post-2010 model, with a higher price, and higher mileage
 is 3.14 times more likely to have a large engine size. Additionally, rule 2 indicates that a car with a
 higher price and higher mileage is 3.14 times more likely to be equipped with a large engine size as
 well. This highlights customer prioritization of power and raw performance. Large engine size also
 shows some positive correlation with higher prices in the data, with rules showing between 15% (Rule
 9) and 25% (Rule 24) correlation strengths on relevant attributes. Customers are willing to pay more
 for a higher engine even if the vehicle has driven a lot of miles.
 There is also a high demand for manual transmission cars. From rule 18, we can see that 86% sold
 cars feature manual transmission, which underscores a sustained market demand for shift-stick
 models. From rule 6, we can see that if a car runs on petrol, there is an 88.9% chance that it is a
 manual car. This rule supports the enduring higher demand for petrol manual cars, even for newer
 post-2010 vehicle models.
 Rule 5 shows that for a post-2010 petrol model, there is 88.9% that the car is manual. Rule 21
 indicates that if the car is manual, there is 98% that the car is an after-2010 model. We can interpret
that petrol cars, especially those produced after 2010, tend to be manual transmissions. Lastly, when a
 car is identified as a higher-priced vehicle, there is a 42.10% confidence that it will have a manual
 transmission. In practical terms, this association could imply that a significant portion of higher-priced
 cars in the dataset tends to come with manual transmissions.

 ## Predictive Statistics

  Data cleaning: We grouped the vehicles in the dataset based on the 'Model' column into four distinct
 categories: SUV, sedan, MPV (Multi-Purpose Vehicle), and Convertible. After creating the new
 'Vehicle Type' column with these groupings, we proceeded to drop the original 'Model' column from
 the dataset.

 ### Multiple Linear Regression

 ![image](https://github.com/SarthakJN99/Ford-Secondary-Vehicles-Analysis-/assets/144856781/182db86a-1054-4576-9479-a8a83a6c751a)

  In this multiple linear regression analysis, price is the
 dependent variable, and various independent variables
 are examined to understand their impact on the price
 of Ford vehicles.
 Transmission Type (Manual, Semi-Auto, and
 Automatic): The automatic transmission serves as the
 reference group. The manual transmission is
 anticipated to be priced about $756.37 lower than the
 automatic transmission. Similarly, the semi-automatic
 transmission also shows a lower cost of $152.49
 compared to the automatic transmission, although this
 difference is statistically insignificant.
 Mileage: Mileage reflects how much the car has been
 driven. For each additional mile on the car, the
 estimated price decreases by $0.064. This relationship
 is statistically significant.
Fuel Type (Diesel, Petrol, Hybrid, and Other): Diesel cars serve as the reference group. Hybrid cars
 are the most expensive, costing about $8,030 more than diesel cars. If it is an electric car or other
 fuel-type car, its price is estimated to be about $829.8 and $179 higher compared to a diesel car,
 respectively. On the other hand, petrol cars are around $2,370 cheaper than diesel cars. The output for
 petrol and hybrid cars shows statistical significance.
 Vehicle Type (MPV, Sedan, SUV, and Convertible): Convertibles serve as the reference group. All
 of these groups seem to have a lower price compared to Convertibles. MPVs (Multi-purpose vehicles)
 with an estimated price decrease of $7,377, followed by Sedans with a $5,875 reduction, and SUVs
 with a $5,980 price dip. They are all statistically significant.
 mpg: With an increase of every one mile per gallon, the estimated price of the vehicle tends to
 decrease by $139. This result displays statistical significance as well.
 Engine Size: For every increase of 0.1 liters in engine size, the model suggests that the price of the
 vehicle tends to rise by $3,096. This result demonstrates statistical significance as well.
 Year: The positive coefficient (1,127.948) indicates that as the model year of the vehicle increases, the
 price tends to rise by $1,127.95. This relationship is statistically significant.
 The linear regression model explains about 75.7% of the variability in Ford vehicle prices. The low
 residual standard error (2,340.970) implies that, on average, the actual prices of Ford vehicles differ
 from predicted values by approximately $2,340. A highly significant F statistic (4,218.923, df =
 13;17597, p<0.01) indicates the overall statistical significance of the model, reinforcing its
 effectiveness in predicting vehicle prices. The analysis yields compelling insights: Manual
 transmission cars emerge as the budget-friendly option, while automatics claim the premium tier.
 When it comes to fuel type, petrol vehicles boast the most economical price point, with hybrids
 securing the highest. Delving into vehicle preferences, the narrative unfolds with MPVs championing
 affordability and convertibles commanding the highest price.
 We hypothesized the presence of multicollinearity between "Year" and "Mileage." Confirming our
 hypothesis, the correlation coefficient of-0.7078 suggests a high correlation (negative linear
relationship) between these variables. Given this correlation, we conclude that multicollinearity exists
 in the dataset. Consequently, reliance on our multiple linear regression (MLR) model for precise
 predictions of price based on variables of year and mileage may be compromised due to the
 challenges multicollinearity poses in isolating the individual effects of these correlated predictors.

 ### K Nearest Neighbors vs Regression Tree

 Initially, a loop was executed to determine the Root Mean Square Error (RMSE) for both the
 K-Nearest Neighbors (KNN) and Regression Tree models. The optimal value for K in KNN was
 identified as 14, yielding an RMSE of 3896.73, while for the Regression Tree model, the optimal
 minimum deviation value was 0.0005, resulting in a lower RMSE of 1964.297. The decision was
 made to choose the Regression Tree model for price prediction due to its performance with a lower
 RMSE.
 Subsequently, a new dataset was created to apply the Regression Tree for price prediction. Three cars
 were predicted using the Regression Tree model. For Car 1, with specifications including 30,000
 miles, 50 mpg, an engine size of 1, model year of 2017, identified as an MPV with Automatic
 transmission and Diesel fuel type, the predicted price is $11,739.131. For Car 2, featuring 15,768
 miles, 20 mpg, an engine size of 1.5, manufactured in 2017, identified as a Sedan with Semi-automatic
 transmission and Hybrid fuel type, the predicted price is $5,062.364. For Car 3, featuring 10,000
 miles, 40 mpg, an engine size of 2, manufactured in 2020, identified as a Convertible with Automatic
 transmission and Hybrid fuel type, the predicted price is $39,689.235.

 ### Regression Tree

 In plot 8, we can see that our dependent variable, the price of a used Ford car, is influenced by several
 independent variables, which include the Year, Engine Size, Vehicle Type, and MPG. Our tree plot
 using the specific MINDEV of 0.005, has been grouped in several ways including, Engine size
 (Engine Size<1.9, Engine Size<1.75, Engine Size<1.35, Engine Size<1.05, Engine Size<2.15), year
 (year<2018.5, year<2015.5, year<2012.5, year<2017.5), vehicle type (vehicle_type_SUV, Vehicle
 Type_Convertable), and MPG (MPG<51.85, MPG<57.1, MPG<37.4).

 ![image](https://github.com/SarthakJN99/Ford-Secondary-Vehicles-Analysis-/assets/144856781/86e2dac5-2b10-4ccb-b22a-21fab9e4bd95)

 In delving deeper into our tree plot, it's crucial to note that our model incorporates the entirety of our
 training data. The top-down structure of the model entails that all data points in the training sample,
 such as those predating the Year 2018.5, are directed to the left-hand side of the tree. Here, the left
 side represents instances where the condition is met (equal to one), while the right side denotes
 scenarios where the condition is not met or equals zero. Consequently, this right side encompasses
 cars produced after the year 2018.5. The visualization also reveals significant insights, aiding us, for
 instance, in discerning the most high-priced category among Ford Used Cars. Specifically, this
 pertains to car types that are not dated before the year 2018.5 (or those produced post-2018.5).
 Consequently, as the condition is not met, these instances flow towards the right side of the plot.
 Further examination shows that this category includes cars with an engine size not less than 1.75
 (indicating an engine size greater than 1.75). Notably, among these, the most expensive variant is a
 convertible priced at $39,690, as depicted in our tree plot.
 Our tree plot also unveils insights into the most economical category of Ford used cars within our
 dataset. In this context, we identify a car type that predates the year 2018.5. Given that this condition
 is met, these instances flow towards the left side of the plot. Further criteria include a car type with an
 engine size smaller than 1.9, older than the year 2015.5, and preceding the year 2012.5. Notably,
 within this segment, we find the least expensive car, priced at $3,841, as outlined in our tree plot.
Interestingly, our interpretation reveals a correlation between newer cars and higher prices. This is
 evident in the data, where Ford used cars meeting the condition of being produced before the year
 2018.5 (flowing to the left side of the tree) exhibit a lower average price of $12,494. In contrast,
 instances where the condition is not met, indicating cars produced after the year 2018.5, are
 significantly more expensive with an average price of $21,618.5. Furthermore, our analysis of the tree
 plot highlights another key observation: cars with larger engine sizes (specifically, those greater than
 1.9 and 1.75) tend to command higher prices compared to their counterparts with smaller engine sizes.
 These insights contribute to a comprehensive understanding of the pricing dynamics within the Ford
 used car market.

 ## Major Takeaways
 
 The linear regression and regression tree analyses offer valuable insights into the determinants of Ford
 used car prices. Both models highlight the positive correlation between the model year and pricing,
 emphasizing the impact of newer vehicles on higher costs. Transmission types play a crucial role, with
 manual transmissions identified as more budget-friendly in the linear regression model. The regression
 tree provides a visual representation of nuanced interactions, indicating that cars produced
 post-2018.5 are significantly more expensive. Engine size emerges as a consistent factor influencing
 prices, with both analyses revealing higher costs associated with larger engine sizes. Vehicle types
 also contribute to pricing dynamics, with the linear regression estimating specific price reductions for
 MPVs, sedans, and SUVs compared to convertibles. The linear regression model warns of
 multicollinearity between year and mileage, highlighting potential challenges in isolating their
 individual effects on pricing.

 ## Implications/Suggestions
 
 For dealerships, strategic pricing considerations can significantly enhance sales and customer appeal.
 Recognizing the impact of engine size on performance, dealers should position vehicles with larger
 engines at higher price points, aligning with the elevated capabilities and driving experiences these
 models offer. Additionally, emphasizing lower mileage as a pricing factor can attract buyers seeking
well-maintained and reliable options, creating a value proposition for these vehicles. Convertible
 models with substantial engines should be strategically priced higher, tapping into the unique market
 value associated with open-top driving experiences. Furthermore, acknowledging the premium status
 of hybrid vehicles, dealerships can set prices that reflect the value of fuel efficiency and environmental
 consciousness, potentially increasing revenue compared to non-hybrid counterparts.
 Manufacturers should dual-focus on fuel-efficient vehicles to meet eco-friendly demand and
 high-performance cars for driving enthusiasts. Balancing both aspects diversifies offerings, broadens
 appeal, and ensures competitiveness, optimizing pricing strategies for profitability and customer
 satisfaction







 

 
