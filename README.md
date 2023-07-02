# ANALYZING-THE-NYC-TAXI-TRIP-USING-PYTHON
As an analyst you have been tasked with analyzing the datasets of the new york taxi trip to get insight to help improve services .
The dataset consist of

vendor id

tpep_pickup_datetime

tpep_dropoff_datetime

passenger_count

trip_distance

RatecodeID

store_and_fwd_flag

PULocationID

DOLocationID

payment_type

fare_amount

extra

mta_tax

tip_amount

tolls_amount

improvement_surcharge

total_amount

First
we import the relevant packages and libaraies for the analysis

importing numpy for numerical analysis

pandas for analysing our dataset

matplotlib and seaborn for data visualization.

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
now we load the dataset into the dataframe

pd.read_csv('yellow taxi trip nyc.csv')


now we rename the dataset

ytt = pd.read_csv('yellow taxi trip nyc.csv')
then we find details included in the column

ytt.columns

now we do some cleaning on our dataset .

ytt.isnull().sum()

now we find the shape of our dataframe using the shape function.

ytt.shape

now we can see that our dataset has 22699rows and 18 columns.

so we go ahead to find the the first 10 datasets using the head function.

ytt.head(10)


WE use the nfo function now to know the details of our dataset.

ytt.info()

Using the sort function to remove datasets not relevant to our analysis.

ytt_sort = ytt.sort_values(by=['trip_distance'],ascending=False) 
ytt_sort.head(10)


we get the statistical insight of our dataset using the describe function.

ytt.describe()


Question 1:
what is the min, mean and max of your first variable ?

Answer:
Min Mean Max

total_amount -120.30 , 16.31 , 1200.29

Question 2:
what is the min, mean, and max of your second variable?

Answer:
Min Mean Max trip_distance 0 , 2.91 , 33.96

we plot a histogram to observe the distribution level of our dataset.

plt.figure(figsize=(8,6))
plt.xticks(fontsize=14); plt.yticks(fontsize=14)
ytt = ytt.sort_values(by='total_amount')
plt.hist(ytt['total_amount'],bins=[0,20,40,60,80,100])
plt.title('Histogram of Total Amount',fontsize=20)
plt.xticks(fontsize=15); plt.yticks(fontsize=15)
plt.xlabel('$ amount bin',fontsize=20)
plt.ylabel('Count', fontsize=20)

Now we can see that for the amount we have an even distribution .

now we check for trip distance to see how even it is

plt.figure(figsize=(8,6))
#plt.xticks(fontsize=14); plt.yticks(fontsize=14)
ytt = ytt.sort_values(by='trip_distance')
plt.hist(ytt['trip_distance'],bins=[0,5,10,20,25])
plt.title('Histogram of Trip Distance',fontsize=20)
plt.xticks(fontsize=15); plt.yticks(fontsize=15)
plt.xlabel('Trip distance bin',fontsize=20)
plt.ylabel('Count', fontsize=20)

We can observe by the histogram that our amount category and trip distance is evenly distributed……






