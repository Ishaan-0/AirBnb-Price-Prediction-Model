# Airbnb Price Prediction Deep Learning Model  

## Overview  
This project aims to predict Airbnb listing prices using a deep learning model. The dataset was highly skewed, which required careful preprocessing and handling of missing values. The model was developed to understand how various features such as location, property type, and amenities affect the price of a listing.  

---

## Dataset Description  
The dataset includes the following features:  
- **id** – Unique identifier for the listing  
- **log_price** – Log-transformed price of the listing (target variable)  
- **property_type** – Type of property (e.g., Apartment, House)  
- **room_type** – Type of room offered (e.g., Entire home/apt, Private room)  
- **amenities** – List of amenities available at the property  
- **accommodates** – Number of guests the property can accommodate  
- **bathrooms** – Number of bathrooms in the listing  
- **bed_type** – Type of bed provided (e.g., Real Bed, Futon)  
- **cancellation_policy** – Cancellation policy of the host (e.g., Moderate, Strict)  
- **cleaning_fee** – Indicates if a cleaning fee is charged (TRUE/FALSE)  
- **city** – City where the property is located  
- **description** – Description of the property provided by the host  
- **first_review** – Date of the first review for the listing  
- **host_has_profile_pic** – Indicates if the host has a profile picture (t/f)  
- **host_identity_verified** – Indicates if the host's identity is verified (t/f)  
- **host_response_rate** – Host's response rate (e.g., 100%)  
- **host_since** – Date when the host joined Airbnb  
- **instant_bookable** – Indicates if the listing can be booked instantly (t/f)  
- **last_review** – Date of the most recent review for the listing  
- **latitude** – Latitude coordinate of the listing's location  
- **longitude** – Longitude coordinate of the listing's location  
- **name** – Name/title of the listing  
- **neighbourhood** – Neighborhood where the listing is located  
- **number_of_reviews** – Total number of reviews the listing has received  
- **review_scores_rating** – Average review score for the listing  
- **thumbnail_url** – URL for the thumbnail image of the listing (may be empty)  
- **zipcode** – Zip code of the property's location  
- **bedrooms** – Number of bedrooms in the listing  
- **beds** – Number of beds in the listing  

---

## Data Preprocessing  
### 1. **Feature Engineering**  
- Created a new feature **host_experience** by extracting the number of years since the host joined Airbnb (from the `host_since` column).  

### 2. **Handling Missing Values**  
- Filled missing numeric values with the **median**.  
- Filled missing categorical values with `'f'`  where appropriate.  

### 3. **Encoding**  
- Used **One-Hot Encoding** for categorical features like `property_type` and `neighbourhood`.  
- Used **Label Encoding** for binary and ordinal features like `host_has_profile_pic`, `host_identity_verified`, and `instant_bookable`.  

### 4. **Scaling**  
- Applied **RobustScaler** to handle skewed data and scale numeric values.  

---

## Model Development  
### 1. **Baseline Model (Regressor)**  
- Built a baseline model using a standard regression model for comparison.  

### 2. **Deep Learning Model**  
- Developed a deep learning model using **Keras** and **TensorFlow** with the following architecture:  
   - Input Layer  
   - Hidden Layers (with ReLU activation)  
   - Dropout Layers (to prevent overfitting)  
   - Output Layer (for regression)  

- **Loss Function**: Mean Squared Error (MSE)  
- **Optimizer**: Adam (learning rate = 0.001)  
- **Metrics**: Mean Absolute Error (MAE)  

---

## Results  
- **Baseline Regressor**: Achieved reasonable performance on the test set.  
- **Deep Learning Model**: The performance was slightly worse than the baseline regressor.  

