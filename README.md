# Will the Customer Accept the Coupon?

## Overview

This project looks at what makes drivers accept or reject coupons delivered to their phones while driving. The data comes from a survey on Amazon Mechanical Turk and includes different driving scenarios (weather, time of day, passengers, destination) along with driver demographics.

I focused on two coupon types: **Bar** and **Coffee House**.

## Data

The dataset has 12,684 survey responses with 26 features including:
- Driver info (age, income, occupation, etc.)
- Driving context (destination, weather, time, passengers)
- Coupon details (type, expiration)
- Whether they accepted (Y = 1) or rejected (Y = 0)

One column (`car`) was dropped due to 99% missing values.

## Key Findings

### Bar Coupons (41% overall acceptance)

The biggest factor is how often someone already goes to bars:
- Drivers who go to bars >3 times/month: **77% acceptance**
- Drivers who go ≤3 times/month: **37% acceptance**

Other factors like age, passengers, and marital status had smaller effects. Frequent bar-goers accept at high rates regardless of these other factors.

### Coffee House Coupons (50% overall acceptance)

Similar pattern with visit frequency, but context matters more:
- Frequent coffee house visitors: **68% acceptance**
- Infrequent visitors: **45% acceptance**

Time of day made a big difference:
- 10AM: **64%** (mid-morning coffee break)
- 7AM: **45%** (rush hour, no time to stop)
- 6PM: **41%** (evening, competing with other options)

Social context also mattered — drivers with friends (60%) or partners (57%) accepted more than those alone (44%).

## Recommendations

**For bar coupons:**
- Target frequent bar-goers — they're twice as likely to accept
- Don't waste coupons on infrequent visitors

**For coffee house coupons:**
- Deliver around 10AM for best results
- Target drivers with passengers
- Avoid drivers heading home (lowest acceptance at 36%)

## Files

- `prompt.ipynb` — Jupyter notebook with full analysis
- `data/coupons.csv` — Dataset

## Next Steps

- Build a predictive model using these features
- Look at the other coupon types (Restaurant, Carry Out)
- Test whether combining factors improves targeting


