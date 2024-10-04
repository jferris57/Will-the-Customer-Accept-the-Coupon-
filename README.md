# Will the Customer Accept the Coupon?

## Context
Imagine driving through town and a coupon is delivered to your cell phone for a restaurant near where you are driving. Would you accept that coupon and take a short detour to the restaurant? Would you accept the coupon but use it on a subsequent trip? Would you ignore the coupon entirely? What if the coupon was for a bar instead of a restaurant? What about a coffee house? Would you accept a bar coupon with a minor passenger in the car? What about if it was just you and your partner in the car? Would weather impact the rate of acceptance? What about the time of day?

Obviously, proximity to the business is a factor on whether the coupon is delivered to the driver or not, but what are the factors that determine whether a driver accepts the coupon once it is delivered to them? How would you determine whether a driver is likely to accept a coupon?

The goal of this project is to distinguish between customers who accepted a driving coupon versus those that did not. You can find a link to my Jupyter notebook detailing my work [here](https://github.com/jferris57/Will-the-Customer-Accept-the-Coupon-/blob/main/Will_the_Customer_Accept_the_Coupon_.ipynb).

## Findings
The first step in the data cleaning process was taking a look at the missing values. I noticed the 'car' column had a ton of missing values. After looking deeper, the only values in that column were not useful so I removed it entirely. Then I dropped the missing data from the rest of the dataset.

First I determined the proportion of the total observations that chose to accept the coupon was 0.569 (56.9%).

Then I plotted the different types of coupons by count:
![image](https://github.com/user-attachments/assets/3a58aed9-707c-4440-903d-0653d4f474f1)

Then I plotted the different types of coupons and their acceptance rates:
![image](https://github.com/user-attachments/assets/73ec4ee7-b256-4a79-b89e-08ce357419f1)

### Bar coupons
I began to look at just the bar coupons specifically. I found that out of these, 0.411 (41.1%) were accepted.

As we dive deeper, I found that the drivers who visit bars more than 3 times a month were much more likely to accept a coupon:
![image](https://github.com/user-attachments/assets/28123c95-a8a2-4fd6-b55d-52979d788ace)

Then I looked at the acceptance rates of those who visit bars more than once a month and are over the age of 25 vs. those who visit less than once a month and under the age of 25. The acceptance rates were 0.689 (68.9%) and 0.388 (38.8%) respectively.

I discovered that drivers were much more likely to accept the coupon when alone or with their friends/partner than when they had passengers that were children.
- Acceptance rate with friends/partner: 0.714 (71.4%)
- Acceptance rate when alone: 0.706 (70.6%)
- Acceptance rate with children: 0.38 (38%)

![image](https://github.com/user-attachments/assets/0ff33b81-efa9-4c65-ade7-439d4d327b10)

We then looked at a few more metrics:
- Acceptance rate of those that visit bars more than once a month, had passengers that were not kids, and were not widowed: 0.714 (71.4%)
- Acceptance rate of those that visit bars more than once a month and under the age of 30: 0.719 (71.9%)
- Acceptance rate of those that go to cheap restaurants (less than $20) and whose income is less than 50k: 0.456 (45.6%)

Based on these observations we can conclude that out of all the coupon types, bar coupons were the least accepted. Of these bar coupons, those who frequent bars more than 3 times a month were much more likely to accept the coupon than those who went less than 3 times a month (76.1% to 37.2%). Drivers who go more than once a month and over the age of 25 were more likely to accept the coupon than those under 25 that visit bars less than once a month. The drivers were also much more likely to accept the coupon when alone, with friends, or with their partner rather than with kids in the car.

### Coffee House coupons
I then began an independent investigation into the coffee house coupons. I asked myself the following questions:
- What was the acceptance rate depending on the destination of the driver?
- What was the acceptance rate depending on the gender of the driver?
- How did the amount of times the driver frequents coffee shops affect acceptance rates?

The destinations were categorized as "No urgent destination, Work, and Home".
- Those with no urgent destination had an acceptance rate of 0.578 (57.8%)
- Those headed to work had an acceptance rate of 0.44 (44%)
- Those headed home had an acceptance rate of 0.362 (36.2%)

![image](https://github.com/user-attachments/assets/3b8d12d8-6bf6-4946-a531-a07dc3e04698)

Although I had an initial inclination that one gender might have a higher acceptance rate than another, both were almost identical.
![image](https://github.com/user-attachments/assets/dee451e1-c13b-4bea-9ce4-6a5886223979)

The amount of times a driver visits coffee shops in a month had a big impact on acceptance rate.
- Those who visit coffee shops less than once a month had an acceptance rate of 0.34 (34%)
- Those who visit coffee shops 1-3 times a month had an acceptance rate of 0.647 (64.7%)
- Those who visit coffee shops 4 or more times a month had an acceptance rate of 0.672 (67.2%)

![image](https://github.com/user-attachments/assets/a0ccdf99-88c3-4fca-807b-4d628980313e)

Based on the observations, we can see that coffee house coupons were offered the most. The acceptance rate for both male and female drivers were basically identical, with a slight edge towards male drivers. These coupons were mostly accepted by drivers with no urgent place to go, followed by those heading to work, and the least amount accepted by those headed home. The amount of times drivers frequented coffee houses in a month also had an effect on acceptance rate. Those who go less than once a month had the lowest acceptance rate, those who went 1-3 times were in the middle, and the highest acceptance rate was by those who visit 4 or more times a month.

### Next steps
With just a high level analysis of this data, there is already a story that can be told and a lot to be learned. My next steps would be to dive deeper into the data and break down these comparisons even further. We can look into the other coupons, look at the distances of the destination to the store, the expiration date, etc. Was it raining or sunny when the driver was on their way to their destination? There is so much more than be discovered with deeper analysis.
