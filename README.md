# Predicting Hotel Cancellations
By Kilmar Lazo

Hotel cancellations affect forecasting and controls, the two fundamental elements of revenue management. Being able to predict whether the hotel reservation will be cancelled will help hotel owners and managers increase revenue for the hotel business.

![image](https://user-images.githubusercontent.com/110120531/216509069-2569a3df-085f-461c-92d8-052b16fbf1c0.png)

## Business Understanding

**Business Stakeholder**
- Hotels

**Business Problem**
- Predict hotel cancellations to increase revenue and operate efficiently

**Benefits**
- Improved efficiency
- Increased revenue
- Enhanced customer satisfaction
- Reduced costs
- Improved decision-making

Therefore, both the hotels and guests can benefit from this model, but we will focus more on the hotels for this specific problem.

## Data Understanding
Hotels would require the data related to hotel bookings and whether their bookings were cancelled or not. Kaggle has a dataset
(https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) that provides booking information for a resort hotel and city hotel.

This Kaggle dataset is suitable as it contains useful information about the guests. We will explore the data, build machine learning models, and evaluate the performance of the models. 

**Variables in dataset:**

- hotel: Type of hotel
- is_canceled: Our target variable. Value indicating if the booking was canceled (1) or not (0)
- lead_time: Number of days that elapsed between the entering date of the booking into the PMS and the arrival date
- arrival_date_year: Year of arrival date
- arrival_date_month: Month of arrival date
- arrival_date_week_number: Week number of year for arrival date
- arrival_date_day_of_month: Day of arrival date
- stays_in_weekend_nights: Number of weekend nights (Saturday or Sunday) the guest stayed or booked to stay at the hotel
- stays_in_week_nights: Number of week nights (Monday to Friday) the guest stayed or booked to stay at the hotel
- adults: Number of adults
- children: Number of children
- babies: Number of babies
- meal: Type of meal booked
- country: Country of origin
- market_segment: Market segment designation
- distribution_channel: Booking distribution channel
- is_repeated_guest: Value indicating if the booking name was from a repeated guest (1) or not (0)
- previous_cancellations: Number of previous bookings that were cancelled by the customer prior to the current booking
- previous_bookings_not_canceled: Number of previous bookings not cancelled by the customer prior to the current booking
- reserved_room_type: Code of room type reserved
- assigned_room_type: Code of room type assigned for booking
- booking_changes: Number of changes/amendments made to the booking from the moment the booking was entered on the PMS until the moment of check-in or cancellation
- deposit_type: Indication on if the customer made a deposit to guarantee the booking.
- agent: ID of the travel agency that made the booking
- company: ID of the company/entity that made the booking or responsible for paying the booking.
- days_in_waiting_list: Number of days the booking was in the waiting list before it was confirmed to the customer
- customer_type: Type of booking
- adr: Average Daily Rate as defined by dividing the sum of all lodging transactions by the total number of staying nights
- required_car_parking_spaces: Number of parking spaces required by the customer
- total_of_special_requests: Number of special requests made by the customer
- reservation_status: Reservation last status
- reservation_status_date: Date of last status update

**(Figure 1) Cancellations per Month**

!![image](https://user-images.githubusercontent.com/110120531/216507065-a64edf7a-e1db-41ae-8637-84c577ef9621.png)

- City Hotel’s cancellations were consistent throughout the year
- Resort Hotel faced higher cancellation percentages during the Summer months

**(Figure 2) Effect of Deposit Type on Cancellations**

![image](https://user-images.githubusercontent.com/110120531/216507550-1946545b-2628-47b2-b2e8-3278fc225af5.png)

- Bookings with a non-refundable deposit were almost always cancelled
- Bookings with refundable deposits were least likely to get cancelled

**(Figure 3) Effect of Lead Time on Cancellations**

![image](https://user-images.githubusercontent.com/110120531/216508891-1ea306d3-7060-4157-ba00-92fcba806279.png)

- Lead time has a strong positive correlation with our target variable (is canceled)
- As lead time increases, the chance of cancellation increases

**(Figure 4) Effect of Returning Guests on Cancellations**

![image](https://user-images.githubusercontent.com/110120531/216508921-e4024fe0-5418-4b01-a0a4-660a962bb2ee.png)

- Guests that have never been to the hotel are more likely to cancel their booking
- Returning guests are less likely to cancel their booking

## Modeling and Evaluation

The two models I used were Logistic Regression (baseline model) and Random Forest Classifier. The Random Forest Classifier was tuned using GridSearchCV.

The metrics I used to evaluate the model performance were accuracy score and recall score. 

**(Table 2) Model Performance**
| Model | Accuracy | Recall Score |
|-------|----------|----------------------------|
| Logistic Regression | 81% | 95% |
| Classified Random Forest | 95% | 99% |
| Classified Random Forest Tuned | 87% | 99% |

## Conclusion

**Final Model**
The Random Forest Classifier is the ideal model, as it has an accuracy of 95% and a recall score of 99%.

**Limitations**
The limitations of this dataset is that there may be more factors that affect cancellation, such as the hotel’s location, the number of hotels around the area, and the hotel's rating.

**Next Steps for Improvements**
By gathering more data with extra columns and from more hotels, we would expect our model to perform even better because random forest's performance enhances with a larger data.
Once we have a larger data, we can also implement even more advanced models such as neural network. 

## Repository Navigation

**An explanation of the repository organization**
- hotel_bookings.csv : raw dataset used
- notebook.ipynb : jupyter notebook for EDA, data cleaning, modeling and evaluation
- CapstonePresentation.pdf : final presentation slides

**Links to the final notebook and presentation**
- [notebook.ipynb](.//notebook.ipynb)
- [CapstonePresentation.pdf](.//CapstonePresentation.pdf)

**Reproduction instructions**
- Download the raw dataset from Kaggle. (https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)
- Download [notebook.ipynb](.//notebook.ipynb) to run EDA, perform data cleaning, modeling, and evaluation.

