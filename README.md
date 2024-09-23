Here is a simple **README** for your AirBnB Price Prediction Model:

---

# AirBnB Price Prediction Model

This project involves building a machine learning model to predict the log-transformed price of Airbnb listings based on various features such as property type, neighborhood, review scores, and more.

## Project Overview
The model is built using a dataset containing various attributes related to Airbnb listings. A `RandomForestRegressor` is trained on the dataset to predict the log of the price (`log_price`) based on the features provided. The model includes preprocessing steps such as:
- Label encoding of categorical features.
- Transformation of numerical features using `PowerTransformer` for normalizing the distribution.

### Features Used in the Model:
- `property_type`: Encoded categorical feature representing the type of property.
- `amenities`: The number of amenities available in the listing.
- `accommodates`: Number of people the listing can accommodate.
- `cancellation_policy`: Encoded categorical feature representing the cancellation policy.
- `cleaning_fee`: Cleaning fee charged for the listing.
- `city`: Encoded categorical feature representing the city where the listing is located.
- `host_response_rate`: Host's response rate as a percentage.
- `instant_bookable`: Boolean indicating if the listing is instantly bookable.
- `name`: Encoded name of the listing.
- `neighbourhood`: Encoded categorical feature representing the neighborhood.
- `number_of_reviews`: The total number of reviews the listing has received.
- `review_scores_rating`: The rating of the listing from customer reviews.
- `beds_and_baths`: Sum of bedrooms and bathrooms.
- `price_per_room`: Calculated as log price divided by beds and baths.

## Usage

### 1. Requirements:
- Python 3.6+
- Install required dependencies using:
```bash
pip install -r requirements.txt
```

### 2. Training the Model:
The `RandomForestRegressor` is trained using a dataset after applying the necessary preprocessing steps:
1. **Label Encoding**: Convert categorical variables into numerical values.
2. **Power Transformation**: Apply power transformation to numerical columns to normalize them.

### 3. Prediction:
You can predict the log-transformed price of a listing using predefined inputs for the features mentioned above. The script provides a function `predict_log_price_from_predefined()` which allows you to pass in predefined values for these features and get the predicted log price.

### 4. Converting `log_price` to Actual Price:
Once the log-transformed price is predicted, it can be converted back to the original price using the exponential function:
```python
import numpy as np
original_price = np.exp(predicted_log_price)
```

### 5. Example Usage:
To predict the price for a listing, you can call the function with the predefined values:
```python
predefined_inputs = {
    'property_type': 2,
    'amenities': 10,
    'accommodates': 4,
    'cancellation_policy': 1,
    'cleaning_fee': 50.0,
    'city': 3,
    'host_response_rate': 85.0,
    'instant_bookable': 1,
    'name': 5,
    'neighbourhood': 7,
    'number_of_reviews': 120,
    'review_scores_rating': 90.0,
    'beds_and_baths': 5,
    'price_per_room': 100.0
}
predicted_log_price = predict_log_price_from_predefined()
original_price = np.exp(predicted_log_price)
print(f"Predicted price: {original_price}")
```

## Model Evaluation
The model is evaluated using common regression metrics such as:
- Mean Squared Error (MSE)
- Mean Absolute Error (MAE)
- R-squared (R²)

## License
This project is licensed under the MIT License - see the LICENSE file for details.

---

Let me know if you need any additional information!
