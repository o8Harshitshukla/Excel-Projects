# Hospitality Industry Data Analysis

## Project Overview

In response to the challenging impact of the COVID-19 pandemic on the hospitality industry, this project is dedicated to analyzing booking patterns and evaluating revenue versus losses for small to medium-sized businesses. The primary objective is to provide critical business reporting and visualizations to support informed decision-making in these trying times.

## Input Data

Our analysis is based on several datasets, each serving a unique role in the project:

- **Booking Data**: Contains comprehensive booking-related information.
- **Squad Mapping**: A mapping of multiple cities to squads for reference.
- **Property Details**: Provides revenue data specific to each property.
- **Primary-ID to Property ID Mapping**: A mapping that connects property IDs to primary IDs.

Detailed information about the columns in these datasets is available for reference, helping us make informed and data-driven decisions.

## Output Data

As a result of our analysis, we generate valuable output data, presented in a structured tabular format:

**Table 1: Squad-level Metrics**

![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/ec8c7eba-1189-45ab-9872-f0d5a31bea43)

### Metrics in Table 1

- **Squad**: The unique identifier for each squad.
- **created_at**: The date of booking creation (BCD).
- **total_revenue_per_day**: Total revenue generated for each squad on the booking creation date (BCD). This includes bookings for future dates.
- **current_month_revenue_per_day**: Total revenue generated for each squad on the BCD, limited to bookings for the same month.
- **room_nights_per_day**: The total number of room nights booked for each squad on the BCD.
- **total_cancellation_nights_per_day**: The number of booking nights canceled for each squad on the BCD.
- **total_cancellation_value_per_day**: The revenue lost due to canceled bookings for each squad on the BCD.
- **total_booking_per_month**: The total revenue generated for each squad in the current month (the month corresponding to the BCD).
- **total_room_nights_per_month**: The total number of room nights booked for each squad in the current month.

This table provides a summary of crucial metrics for each squad, enabling businesses to effectively track and analyze their performance in the dynamic and challenging hospitality industry.


***

### Question 1: As we went through the assignment and understood the expectation, we realized that for all KPIs, we have to calculate wrt squad and BCD (booking created_at date). Let’s set up the first columns of our final report.

![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/b1141837-4325-49f3-acb1-585089c5fea3)



**QUESTION-1.1: From which dataset can we get "Booking created at Date (BCD)"?**
![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/26762ba1-6c20-4e02-8d03-4c486f601e9a)


**QUESTION-1.2: Which dataset is most appropriate to get "squad" information with respect to the "Booking created at Date (BCD)" data?**
![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/d10c29fa-e899-4336-809f-379b8ef6d08d)


**QUESTION-1.3: What are the common keys (columns) between the "Booking Data" and "Squad Mapping" datasets?**
![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/ce054907-0655-476d-9174-9c95b3b24f35)


**QUESTION-1.4: Is it possible that the same squad can have multiple bookings on any given day?**
![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/8c740ace-8c33-4e39-bba6-b117fdda9082)


**QUESTION-1.5: How many unique combinations of (Squad, BCD) do we have?**

![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/2dd30f21-a66c-4303-b63b-15fc12b73fa5)


### Question 2: Total Revenue Per Day
![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/3a88eb7c-d95a-45fb-8b28-24dc0c4b16ec)

      We are currently solving **total_revenue_per_day** (highlighted in red).

"Let's delve into a deeper understanding of the Key Performance Indicator (KPI) to ensure its accurate implementation.

This KPI aims to calculate the 'Total revenue for each Squad at BDC (Booking Created Date).' Importantly, this total revenue encompasses bookings for any date – be it in the next month, the same month, or even in the distant future.

For example, let's consider the 'Himachal Pradesh' squad. Our task is to compute the 'total_revenue_per_day' for the specific date, such as '2021-11-08.' When you examine the 'booking data' for 'Himachal Pradesh' on this date, you'll notice numerous bookings occurring on the same day. Our challenge here is to aggregate the revenue from all these individual records.

To elaborate further, what does the bolded statement signify?

'Total revenue for each Squad at BDC (THAT booking created date). This could be for any booking dates, be it next month or the same month or any date in the future.'

This statement emphasizes that we are not restricted to calculating revenue solely for the same month. Instead, we must consider bookings for any date, including those occurring in subsequent months or even further into the future."

This explanation provides a clearer understanding of the KPI's scope and the need for aggregating revenue across various booking dates..


**QUESTION-2.1: What is the Total Revenue Per Day (total_revenue_per_day) for the "Uttarakhand" squad on "2021-05-01"?**

![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/051eb45b-645b-4aea-91db-130a8db4182c)


### Question 3: Current Month Revenue Per Day

![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/47964310-712b-4be9-98af-7f53c863fcf3)

What does it mean?

It means “Total revenue for each Squad at BDC (THAT booking created date). This only needs to be bookings for the same month and not any other months.

           HINT: Use Check-in and check-out date to identify if the booking is for the same month or next”
As per the example given, we need to calculate the total revenue for November only as we are currently looking at “2021-11-08” BCD. Make sense?

It is already highlighted in the KPI explanation that you need to calculate revenue from the bookings (i.e., check-in and checkout) for the same month and not any other months.

Let’s try to identify booking records for the same month or any other months

Which records fall under the same month from the following dates (created_at - checkin - checkout)?

      Note: You can check this data yourself by filtering squad “Himachal Pradesh” with and created_at with “2021-11-08”
![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/94d84b59-12e7-4345-86cf-18172c7f8a70)


**QUESTION-3.1: Now you have identified this manually for few records but we have 13436 records hence we can’t do the same for all records. Create an additional column in the “Booking data” to check how many records are where which has bookings(i.e., check-in and checkout) in the same month as the booking created_at date (BCD).**

![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/0d4601b4-5e52-481a-9acf-cb2925c57634)

**QUESTION-3.2: Find out the number of bookings that end in the same month regardless of the booking created_at date (BCD).**

![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/9b0ae5bf-a240-4df7-a7d1-983f5f55adda)

**QUESTION-3.3: Find out the number of bookings where check-in happened in one month and checkout in the next month.**

![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/216d7ca4-a4a4-4c51-85a9-5560784cd22f)

**QUESTION-3.4: Find out the number of bookings where check-in happened in one month and checkout in the next-to-next month.**
![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/52524474-7fc4-4129-af7c-0712ceb39a2d)


### Question 4 to 16: More Current Month Revenue and Metrics

**QUESTION-4. What is "current_month_revenue_per_day" for the "Lonavala" squad on "2021-05-01"?**

 ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/e24dff52-a29b-44cc-867f-fc8432942519)

**QUESTION-5. What is "current_month_revenue_per_day" for the "Lonavala" squad on "2021-06-15"?**
 ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/b49c65b4-7f19-4aba-a16f-16d88f1676a1)

**QUESTION-6. What is "current_month_revenue_per_day" for the "Alibaug" squad on "2021-05-31"**
 ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/9176485b-9425-4ce0-9d78-a9d02117284c)
 
**QUESTION-7. What is "current_month_revenue_per_day" for the "Ooty" squad on "2021-02-26"?**
   ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/86263de6-2098-4594-929f-98e30caa3fac)

**QUESTION-8. What is "current_month_revenue_per_day" for the "Lonavala" squad on "2021-02-27"?**
   ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/677ba804-3ccf-41b8-b5c1-fbd6e0018bc3)

**QUESTION-9. What is "current_month_revenue_per_day" for the "Himachal Pradesh" squad on "2021-07-14"?**
    ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/078191cd-c4ab-4d85-adf8-9ba0bcae114e)

**QUESTION-10. What is "current_month_revenue_per_day" for the "Nashik + Pune" squad on "2021-06-26"?**
    ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/2698165e-3cac-40e3-9dba-6cdd379263ab)

**QUESTION-11. What is "room_nights_per_day" for the "Ooty" squad on "2021-12-20"?**
    ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/f2bcb081-d675-49f9-b161-57834651cc9c)

**QUESTION-12. What is "room_nights_per_day" for the "Goa" squad on "2021-05-04"?**
    ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/3abe0753-29a0-4e92-a714-d8edc80782c9)

**QUESTION-13. What is "total_cancellation_nights_per_day" for the "Ooty" squad on "2021-04-14"?**
    ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/b9f8e219-b196-4a5e-8df3-818ed0f62a55)

**QUESTION-14. What is "total_cancellation_value_per_day" for the "Ooty" squad on "2021-12-20"?**
    ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/7716b582-dd60-4f03-9ead-807d61d4c5f1)
    
**QUESTION-15. What is "total_booking_per_month" for the "Ooty" squad on "2021-12-20"?**
    ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/8d7a96ac-bd6a-4a5c-a442-044d96ec9639)


**QUESTION-16. What is "total_room_nights_per_month" for the "Ooty" squad on "2021-12-20"?**
    ![image](https://github.com/o8Harshitshukla/Excel-Projects/assets/147975255/8adf7223-bf27-43dd-9cad-11ac00f691de)

***
