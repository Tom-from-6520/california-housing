# 1980 California housing price prediction 

This is an AI/ML project to predict 1980 California districts housing prices.

## Data

I used the dataset of housing prices in California districts collected in 1980 census. The dataset can be found [here] (https://www.kaggle.com/datasets/yasserh/housing-prices-dataset)

## Methods

I first performed some basic explorative steps to get to know the dataset then use different numerical models: linear regression, random forest regression, and sequential tensorflow models.

After those steps, I found that the result are around the 80% accurate mark but does not improve no matter how many different hyperparameter I experimented with.

I had a "feeling" or intuition that the housing prices are somewhat "sticky" to the historically expensive cities, in a sense that are similar to how the trading markets have "memories" of past price points (See [here](https://www.investopedia.com/terms/m/memory-of-price-strategy.asp) for more details).

So, to assess and quantify this intuition, I set out to create a "sieve" of longitude and latitude, and for each district, I add the distance between that district and each of the coordinates in the sieve. And this not only proves that some coordinates are significant impact towards the housing prices but also more impactful than some other reasons I had considered before.

![the sieve over California](https://github.com/Tom-from-6520/california-housing/assets/24250422/c6cbd0ed-b487-4307-be31-cd0814996b33)


Here are the coordinates that have the most impact on the housing prices

![important coordinates](https://github.com/Tom-from-6520/california-housing/assets/24250422/88ed0d56-5a4c-4850-8cb8-8efaefaf6bc4)

## Result

With the expansion of the dataset with the distance-to-sieve-coordinates columns, I was able to achieve 85% accuracy with random forest regression model. While the addition accuracy is small, I consider this expansion important because there are many attributes to the housing prices, such as location of big employers, historical sites, etc., that were left out in the original dataset but were significant to the prices was represented in this expansion.
