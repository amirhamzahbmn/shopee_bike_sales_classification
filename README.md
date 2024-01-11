# Shopee_Bike_Sales_Classification

This was my submission for a capstone project for a Data Science Bootcamp under [General Assembly](https://www.generalassembly.my/courses/data/data-science-bootcamp/) for the [Kyouth Development Programme 2023](https://www.khazanah.com.my/careers/k-youth/). This project utilizes the scraper that I've made previously [here](https://github.com/amirhamzahbmn/shopee_scraperv2). My slides for the project can be seen [here](https://github.com/amirhamzahbmn/shopee_bike_sales_classification/blob/main/Capstone%20Presentation.pdf).

## Introduction

This model was made to predict the categories of products based on their product name. Now it has become increasingly hard for me to directly scrape data from Shopee due to changes made in their APIs. As a result future data that is obtained via the scraper utilizes another API that has limited data. Data that is pulled from this API does not contain information on the product's categories. As a result, a comprehensive analysis of the data cannot be complete without the full scope. I needed the categories for a dashboard I made [here](https://public.tableau.com/app/profile/amirhamzahbmn/viz/shopeebikesales/Dashboard1). The model was capable of predicting a product's category with an F1 score of 89% and was validated with an AUC score of 97%.

## Project Flow

### EDA
- An extensive amount of cleaning was done as raw data consists of strings values pulled from json files. Whole process is covered in the [ipynb file](https://github.com/amirhamzahbmn/shopee_bike_sales_classification/blob/main/TFIDF_Approach.ipynb).
- Initially I planned to keep the cleaning into a minimum as I did not want information to be lost as I wanted the training dataset to resemble the scraped data as much as possible. However due to the fact that the scraped data was only done on Bike shops, naturally the there would be an imbalance with bike related products and non bike related products. Therefore, I was okay with removing non-bike related products from the training pool.
- Although it was reduced, a major imbalance was still present with a 6:1 ratio between the top and runner up class.
- Started out with a total of 54 leaf categories and 54041 samples, dropped down to 10 leaf categories and 49273.
- Removed 'others' category as it was shown to disrupt the models predictions due to its vagueness as a category.

### Modeling
- A Flat approach rather than a hierarchical approach was used to classify the categories. AKA 'Cycling & Skates/Safety Equipment' instead of predicting each level separately.
- A TFIDF approach was used to tokenize the names.
- Base model evaluation was done to determine the best models to be used. LinearSVC, Logistic Regression and Random forest were the clear winners here.
- Random forest was shown to be best model after reducing and "tuning".

### Validation
- An ROC curve plotted was done to visualize the model's capabilities in distinguishing between categories as well as obtaining the AUC score.
- A coefficient analysis of the categories was done to see what tokens were contributing towards the prediction of each class. This is to ensure if any stop words were to be implemented.
- Used fresh new data to predict with the model.

## Limitations
- Due to the fact that the model has been trained from 1 static period only, it will not be able to correctly predict new unseen categories. Unless I find a fix for my data scraper, this model can't be retrained with new data.
- This model did not go through hyperparameter tuning, my machine is a 10 year old laptop, running one iteration already lasted 2 hours. Due to the time constraint of meeting the project deadline, this was skipped. Therefore, results could be better if tuned.

## Future outlook 
- Really want to try out using pre-trained models such as BERT, will look into this once I've gotten myself a better machine.
- Definitely want to revisit my data scraper to obtain data for training the model.

## Conclusion
This project was done to circumvent the issue where categories could no longer be obtained with my data scraper. Now it seems that, the data scraper will need to be tuned to obtain the categories in order for the model to stay accurate. I have come full circle. Nonetheless, It was a great learning experience.
