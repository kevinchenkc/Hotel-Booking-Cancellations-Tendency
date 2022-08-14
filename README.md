- ![Slide1](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide01.JPG?raw=True)
Hello, this is project titled 'Hotel Booking Cancellation Tendency' prepared by me, Kevin. In this project, I built Machine Learning Model to predict tendency of hotel customers to cancel their bookings or not. Why do we need to make this kind of prediction and why did Machine Learning needed to solve this case will be answered in this project. 

- ![Slide2](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide02.JPG?raw=True)
Agenda of today's presentation will be started with explanation of project background, follow by solution that we would like to offer and why is Machine Learning so instrumental in this project. After we understand our goals and purpose of this project, we will continue to create our Machine Learning Modelling including preparing our data so that they could be processed by Machine Learning. And lastly, we will summarize outcomes of our Machine Learning and its implications to the business.

- ![Slide3](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide03.JPG?raw=True)
In this project, me as the presenter acted as newly-hired data scientist. I am hired by a luxurious high-end hotel that faced a lot of bookings cancellations from their customers. They need our service to be implemented as soon as possible so that hotel will not lose on Opportunity Cost of having vacant rooms from hotel cancellations. We expected our hotel is a 5-stars hotel since their customers came from every part of the world, and they even maintain queue of waiting list customers where a customer could have waited for more than 2 months before confirmed for a room in our hotel. Vacant rooms did not only cost our hotel potential benefits that could not be realized, but also *domino effect* that could harm not limited to hotel, but also customers, travel agents, and other stakeholders. Solution we offered is to build a Machine Learning Model that could predict and prevent customers with high tendency of cancelling their bookings in the future to make reservation in our hotel.

- ![Slide4](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide04.JPG?raw=True)
Whis is the cancellation cases in hotel could be harmful, didn't they actually bring extra income to the hotel since there are few parts of payment from the customers that will not be refunded/returned if their bookings ended up to be cancelled? From data collected by Forbes in 2014, customers borned more than USD 6 million for non-refundable portion of their bookings payment. Not only it's a lose for customer side, hotel also suffer losses from potential extra 30% income from Foods and Beverages (F&B) service at their hotel, loss from vacant rooms, unreliable demand forecast since customers keep on looking for promotion discount and lower prices on travel agents or hotel's website. Travel agency will also potential commission from customer bookings. This whole scheme only producing __LOSE-LOSE__ trade for all parties and therefore we need to reduce this bookings cancellations practice furthermore. 

- ![Slide5](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide05.JPG?raw=True)
Our hotel maintain waiting list customers so it is impossible for us to have vacant rooms right? Not entirely true, because as illustrated in the calendar, if a customer booked for the whole week and cancelled them near the bookings date, they might need to give up half or more of their bookings payment. But Hotel did not automatically could find any new customers or filled it up with customers from their waiting list because hotel staff need to find customers that searching for exactly that type of room, exactly the time available and most of them might not want to stay for that long anyway. So at the end, we could not really expect this vacant rooms could be entirely filled up with customers and producing that income from room bookings.

- ![Slide6](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide06.JPG?raw=True)
What we offer is we will build a Machine Learning Model that could reduce False-Negative cases, a condition where we expect customer will not cancel their bookings and they turns out cancelling them, which cause implications explained before.

- ![Slide7](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide07.JPG?raw=True)
If our Machine Learning Modelling could distinguish cancel and not cancel customers entirely, potential benefit from this implementation could bring up to USD 4.7 million for the hotel each year.

- ![Slide8](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide08.JPG?raw=True)
Next we will start with the dataset, there are 11 columns includes the target/label column. These are only information provided by the Hotel, without any details on hotel's location, cancellation policy or occupation rates. In this data, there is no single column that could be give any unique value compared to other line so duplicated items are normal. Every single line of data in this data represent single booking made and the outcome, whether it got cancelled or not. There are few customers that did not fill in their country of origin so we fill it with 'Others'.

- ![Slide9](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide09.JPG?raw=True)
Our label target is information whether booking was cancelled or not. If cancelled, value 1 will be given, and 0 if not cancelled. From the chart, values in target column is not imbalance but we could also interpret that number of cancellations are actually really high. There are at least 1 cancellation in every 3 bookings. As we want to reduce False-Negative cases, we will use Recall(+) as our metrics since by the equation, False-Negative act as the denominator, means the higher the False-Negative cases, Recall(+) score will going down, vice versa.

- ![Slide10](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide10.JPG?raw=True)
After we run our Base Model with Logistic Regression, KNN, SVM, Decision Tree and Random Forest, we could see that 3 most potential models are KNN, Decision Tree and Random Forest which produce recall score a little bit above and under 0.7 and False-Negative cases around 1700-1800 cases.

- ![Slide11](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide11.JPG?raw=True)
From the classification report, it shows that the score is indeed as the evaluation matrix.

- ![Slide12](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide12.JPG?raw=True)
For choosing models for hyperparameter tuning, we perform benchmarking using cross-validation. The result is the same, those 3 best models produce the most promising result with considerable standard deviation.

- ![Slide13](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide13.JPG?raw=True)
We perform hyperparameter tuning to KNN with help of GridSearch and with combination of 1 neighbors, uniform weight and manhattan distance, we could produce recall score above 0.8 which is ideal and very stable model with the training set, and significantly lower number of False-Negative cases. We will compared this result with other algorithms after tuning.

- ![Slide14](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide14.JPG?raw=True)
Hyperparameter tuning to Decision Tree with help of RandomizedSearch did not produce improvement from base model, and overall result is underwhelm.

- ![Slide15](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide15.JPG?raw=True)
Similar to Decision Tree, Random Forest algorithm also could not produce expected recall score of 0.8 and not better than KNN.

- ![Slide16](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide16.JPG?raw=True)
We choose KNN algorithm with parameters of 1 neighbor, uniform weight and manhattan distance as our best model as it already produce the result we hoped for. 

- ![Slide17](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide17.JPG?raw=True)
Since Machine Learning could not reduce False-Negative cases to 0, potential benefits that could be reap from this implementation are reduced to USD 3.7 million and its still a very good economic value.

- ![Slide18](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide18.JPG?raw=True)
As this Machine Learning could offer huge economic value, we recommend it to be implemented straight away. In addition, we also deemed management to re-review their Hotel Cancellations Policy if its the root cause why there were many cancellations happened in the hotel. Then, we also recommend management to make sure all facilities and employees are ready for full-packed rooms since we designed this hotel to not have any single vacant rooms any day of the year.

- ![Slide19](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide19.JPG?raw=True)
Limitation of this project is obviously size of hotel and services, since our hotel is welcoming customers from all over the world, our Model could only work for luxurious hotels that maintain waiting list customers. For the improvement to this project, we would glad if in the next project we could obtain Hotel Cancellation Policy and Hotel Occupation Rate for the least so that we could analyze the hotel more thoroughly.

- ![Slide20](https://github.com/kevinchenkc/Hotel-Booking-Cancellations-Tendency/blob/main/Images/Slide20.JPG?raw=True)
Thank you for your attention, for critics and collaborations please reach me on any social media with username @kevinchenkc. 
