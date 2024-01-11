# Shopee_Bike_Sales_Classification

This was my submission for a capstone project for a Data Science Bootcamp under [General Assembly](https://www.generalassembly.my/courses/data/data-science-bootcamp/) for the [Kyouth Development Programme 2023](https://www.khazanah.com.my/careers/k-youth/). This project utilizes the scraper that I've made previously [here](https://github.com/amirhamzahbmn/shopee_scraperv2).

## Introduction

This model was made to predict the categories of products based on their product name. Now it has become increasingly hard for me to directly scrape data from Shopee due to changes made in their APIs. As a result future data that is obtained via the scraper utilizes another API that has limited data. Data that is pulled from this API does not contain information on the product's categories. As a result, a comprehensive analysis of the data cannot be complete without the full scope. The model was capable of predicting a product's category with an F1 score of 89% and was validated with an AUC score of 97%.

## Project Flow


## Limitations
- Due to the fact that the model has been trained from 1 static period only, it will not be able to correctly predict new unseen categories. Unless I find a fix for my data scraper, this model can't be retrained with new data.
- This model did not go through hyperparameter tuning, my machine is a 10 year old laptop, running one iteration already lasted 2 hours. Due to the time constraint of meeting the project deadline, this was skipped. Therefore, results could be better if tuned.

## Future outlook
- Really want to try out using pre-trained models such as BERT, will look into this once I've gotten myself a better machine.
- Definitely want to revisit my data scraper to obtain data for training the model.

## Conclusion

