# Data for Lectures 1 to 4

RetailCorp is a fictional Danish online retailer of home and kitchen goods. It ships orders to customers across Denmark from two warehouses, in Aarhus and Copenhagen, using two parcel carriers. Lectures 1 to 4 follow RetailCorp through questions about delivery times, late deliveries, basket values, customer satisfaction and a newsletter test.

The company and all its data are invented. We simulated the data so that every number in the course can be reproduced and checked. Because we simulated all orders, and not only a sample, Lecture 1 can compare sample results with the true values for the whole population. With real data that is almost never possible, since the population is unknown.

The files are clean: there are no missing or impossible values. Messy data come later in the course, in separate files.

## Files

| File | Rows | Content | First used |
|---|---|---|---|
| `orders_population.csv` | 50,000 | All orders from January to June 2026 (the population) | Lecture 1 |
| `orders_sample.csv` | 200 | A simple random sample of orders from the population | Lecture 1 |
| `survey.csv` | 400 | Customer survey before and after a website redesign | Lecture 3 |
| `newsletter_test.csv` | 10,000 | Newsletter test with two versions, A and B | Lecture 4 |

## Loading a file

```python
import pandas as pd
url = "https://raw.githubusercontent.com/aaubs/AQM-2026/main/data/"
sample = pd.read_csv(url + "orders_sample.csv")
```

## Orders (`orders_population.csv` and `orders_sample.csv`)

One row per order.

| Column | Type | Description |
|---|---|---|
| `order_id` | text | Order number, "RC-000001" and upwards |
| `order_date` | date | Date of the order, 2026-01-05 to 2026-06-28 |
| `warehouse` | text | "Aarhus" or "Copenhagen" |
| `carrier` | text | "Carrier A" or "Carrier B" |
| `region` | text | Danish region of the customer: Hovedstaden, Midtjylland, Syddanmark, Sjælland or Nordjylland |
| `delivery_hours` | number | Hours from order to delivery |
| `late` | 0 or 1 | 1 if the order took more than 48 hours |
| `order_value_dkk` | number | Basket value in DKK |

## Survey (`survey.csv`)

400 customers who answered the same survey before and after a website redesign.

| Column | Type | Description |
|---|---|---|
| `customer_id` | text | Customer number, "C-0001" and upwards |
| `satisfaction_before` | 1 to 10 | Satisfaction before the redesign |
| `satisfaction_after` | 1 to 10 | Satisfaction after the redesign |
| `recommend` | 0 or 1 | 1 if the customer would recommend RetailCorp (asked after the redesign) |

## Newsletter test (`newsletter_test.csv`)

| Column | Type | Description |
|---|---|---|
| `recipient_id` | text | Recipient number, "R-00001" and upwards |
| `version` | text | "A" or "B", 5,000 recipients each |
| `converted` | 0 or 1 | 1 if the recipient bought something within seven days |
