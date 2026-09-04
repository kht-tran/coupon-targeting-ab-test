# Data Dictionary

| Variable Name | Description | Notes |
|---|---|---|
| `id` | Unique customer identifier | |
| `trans_after` | Number of transactions after the experiment | Only available for users in the Test |
| `revenue_after` | Total revenue after the experiment | Only available for users in the Test (USD) |
| `test_coupon` | Whether the user received a coupon | Only available for users in the Test. =1: Yes, =0: No |
| `minority` | Whether the user was predicted to belong to a minority group | Information provided by Trackify (=1: Yes; =0: No) |
| `non_male` | Whether the user was predicted to be non-male | Information provided by Trackify. =1: Yes, =0: No |
| `channel_acq` | Channel of acquisition for the customer when they first signed up to the website | =1: Google, =2: Facebook, =3: Instagram, =4: Referral, =5: Other |
| `num_past_purch` | Number of previous purchases | |
| `spent_last_purchase` | Total spent in previous purchase (USD) | |
| `weeks_since_visit` | Number of weeks since last visit | |
| `browsing_minutes` | Time spent on this website during last visit (minutes) | |
| `shopping_cart` | Whether the user added a product to the shopping cart in last visit (but did not transact) | =1: Yes, =0: No |
