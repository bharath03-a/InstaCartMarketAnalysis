# Instacart Market Basket Analysis

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/7/7c/Kaggle_logo.png" alt="Kaggle" height="100"> 
  <img src="https://d2kq0urxkarztv.cloudfront.net/5fad7c666514100070f6c76e/4102165/image-d1ec0f8e-dc85-46f0-b283-c33fc38d5e2a.png" alt="Instacart" height="120">
</p>

## Overview
Predict which products an Instacart consumer will purchase again.

This repository contains code and resources for the **Instacart Market Basket Analysis** Kaggle competition. The goal is to predict reordered items in users' next orders based on a relational dataset describing their past purchase behavior.

## Dataset Description
The dataset for this competition is a relational set of files describing customers' orders over time. It contains anonymized data from over **3 million grocery orders** across more than **200,000 Instacart users**. For each user, the dataset includes:
- Between 4 and 100 orders
- Products purchased in each order
- Weekday and hour of day when the order was placed
- Relative time between consecutive orders

For more information, see the [official Kaggle competition page](https://www.kaggle.com/c/instacart-market-basket-analysis).

## File Descriptions

### `aisles.csv`
Contains information about product aisles:

| Column     | Description           |
|------------|-----------------------|
| `aisle_id` | Unique ID for each aisle |
| `aisle`    | Name of the aisle     |

### `departments.csv`
Contains information about product departments:

| Column         | Description              |
|----------------|--------------------------|
| `department_id`| Unique ID for each department |
| `department`   | Name of the department   |


### `order_products__*.csv`
Specifies which products were purchased in each order. This file comes in two versions:
- `order_products__prior.csv`: Contains data for all prior orders.
- `order_products__train.csv`: Contains data for training orders.

| Column               | Description                                           |
|----------------------|-------------------------------------------------------|
| `order_id`           | Unique ID for the order                               |
| `product_id`         | Unique ID for the product                             |
| `add_to_cart_order`  | Sequence in which the product was added to the cart   |
| `reordered`          | Indicates if the product was ordered previously       |


### `orders.csv`
Provides metadata about each order, including the user ID and the evaluation set to which the order belongs:

| Column                | Description                                   |
|-----------------------|-----------------------------------------------|
| `order_id`            | Unique ID for the order                      |
| `user_id`             | Unique ID for the user                       |
| `eval_set`            | Dataset type (`prior`, `train`, or `test`)   |
| `order_number`        | Sequence number of the order for the user    |
| `order_dow`           | Day of the week the order was placed         |
| `order_hour_of_day`   | Hour of the day the order was placed         |
| `days_since_prior_order` | Time since the last order                  |


### `products.csv`
Contains details about each product:

| Column         | Description                |
|----------------|----------------------------|
| `product_id`   | Unique ID for the product  |
| `product_name` | Name of the product        |
| `aisle_id`     | ID of the aisle            |
| `department_id`| ID of the department       |


### `sample_submission.csv`
Provides a template for submission:

| Column      | Description                        |
|-------------|------------------------------------|
| `order_id`  | Unique ID for the test set order   |
| `products`  | Predicted product IDs (space-separated) |
