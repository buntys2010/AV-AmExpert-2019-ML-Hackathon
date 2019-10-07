# AV-AmExpert-2019-ML-Hackathon
AmExpert 2019 - Machine Learning Hackathon

<img src='https://github.com/Patil-Sahil/AmExpert-2019-ML-Hackathon/raw/master/AmexTop.png'/>

## Introduction

American Express and Analytics Vidhya presents “AmExpert 2019 – Machine Learning Hackathon”. An amazing opportunity to showcase your analytical abilities and talent.

# Problem Statement

## Predicting Coupon Redemption

XYZ Credit Card company regularly helps it’s merchants understand their data better and take key business decisions accurately by providing machine learning and analytics consulting. ABC is an established Brick & Mortar retailer that frequently conducts marketing campaigns for its diverse product range. As a merchant of XYZ, they have sought XYZ to assist them in their discount marketing process using the power of machine learning. Can you wear the AmExpert hat and help out ABC?

Discount marketing and coupon usage are very widely used promotional techniques to attract new customers and to retain & reinforce loyalty of existing customers. The measurement of a consumer’s propensity towards coupon usage and the prediction of the redemption behaviour are crucial parameters in assessing the effectiveness of a marketing campaign.

ABC’s promotions are shared across various channels including email, notifications, etc. A number of these campaigns include coupon discounts that are offered for a specific product/range of products. The retailer would like the ability to predict whether customers redeem the coupons received across channels, which will enable the retailer’s marketing team to accurately design coupon construct, and develop more precise and targeted marketing strategies.

The data available in this problem contains the following information, including the details of a sample of campaigns and coupons used in previous campaigns -

<b>User Demographic Details </b>

<b> Campaign and coupon Details </b>

<b> Product details </b>

<b> Previous transactions </b>

Based on previous transaction & performance data from the last 18 campaigns, predict the probability for the next 10 campaigns in the test set for each coupon and customer combination, whether the customer will redeem the coupon or not?

# Dataset Description

Here is the schema for the different data tables available. The detailed data dictionary is provided next.

<img src="https://github.com/Patil-Sahil/AmExpert-2019-ML-Hackathon/raw/master/Schema.png" />

You are provided with the following files in train.zip:

<b> train.csv </b> : Train data containing the coupons offered to the given customers under the 18 campaigns

<table>
<thead>
<tr>
<th>Variable</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr>
<td>id</td>
<td>Unique id for coupon customer impression</td>
</tr>
<tr>
<td>campaign_id</td>
<td>Unique id for a discount campaign</td>
</tr>
<tr>
<td>coupon_id</td>
<td>Unique id for a discount coupon</td>
</tr>
<tr>
<td>customer_id</td>
<td>Unique id for a customer</td>
</tr>
<tr>
<td>redemption_status</td>
<td>(target) (0 - Coupon not redeemed, 1 - Coupon redeemed)</td>
</tr>
</tbody>
</table>

<b> campaign_data.csv </b> : Campaign information for each of the 28 campaigns
<table>
<thead>
<tr>
<th>Variable</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr>
<td>campaign_id</td>
<td>Unique id for a discount campaign</td>
</tr>
<tr>
<td>campaign_type</td>
<td>Anonymised Campaign Type (X/Y)</td>
</tr>
<tr>
<td>start_date</td>
<td>Campaign Start Date</td>
</tr>
<tr>
<td>end_date</td>
<td>Campaign End Date</td>
</tr>
</tbody>
</table>

<b> coupon_item_mapping.csv </b> : Mapping of coupon and items valid for discount under that coupon

<table>
<thead>
<tr>
<th>Variable</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr>
<td>coupon_id</td>
<td>Unique id for a discount coupon (no order)</td>
</tr>
<tr>
<td>item_id</td>
<td>Unique id for items for which given coupon is valid (no order)</td>
</tr>
</tbody>
</table>

<b> customer_demographics.csv </b> : Customer demographic information for some customers

<table>
<thead>
<tr>
<th>Variable</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr>
<td>customer_id</td>
<td>Unique id for a customer</td>
</tr>
<tr>
<td>age_range</td>
<td>Age range of customer family in years</td>
</tr>
<tr>
<td>marital_status</td>
<td>Married/Single</td>
</tr>
<tr>
<td>rented</td>
<td>0 - not rented accommodation, 1 - rented accommodation</td>
</tr>
<tr>
<td>family_size</td>
<td>Number of family members</td>
</tr>
<tr>
<td>no_of_children</td>
<td>Number of children in the family</td>
</tr>
<tr>
<td>income_bracket</td>
<td>Label Encoded Income Bracket (Higher income corresponds to higher number)</td>
</tr>
</tbody>
</table>

<b> customer_transaction_data.csv </b> : Transaction data for all customers for duration of campaigns in the train data
<table>
<thead>
<tr>
<th>Variable</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr>
<td>date</td>
<td>Date of Transaction</td>
</tr>
<tr>
<td>customer_id</td>
<td>Unique id for a customer</td>
</tr>
<tr>
<td>item_id</td>
<td>Unique id for item</td>
</tr>
<tr>
<td>quantity</td>
<td>quantity of item bought</td>
</tr>
<tr>
<td>selling_price</td>
<td>Sales value of the transaction</td>
</tr>
<tr>
<td>other_discount</td>
<td>Discount from other sources such as manufacturer coupon/loyalty card</td>
</tr>
<tr>
<td>coupon_discount</td>
<td>Discount availed from retailer coupon</td>
</tr>
</tbody>
</table>

<b> item_data.csv </b> : Item information for each item sold by the retailer

<table>
<thead>
<tr>
<th>Variable</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr>
<td>item_id</td>
<td>Unique id for itemv</td>
</tr>
<tr>
<td>brand</td>
<td>Unique id for item brand</td>
</tr>
<tr>
<td>brand_type</td>
<td>Brand Type (local/Established)</td>
</tr>
<tr>
<td>category</td>
<td>Item Category</td>
</tr>
</tbody>
</table>

<b> test.csv </b> : Contains the coupon customer combination for which redemption status is to be predicted
<table>
<thead>
<tr>
<th>Variable</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr>
<td>id</td>
<td>Unique id for coupon customer impression</td>
</tr>
<tr>
<td>campaign_id</td>
<td>Unique id for a discount campaign</td>
</tr>
<tr>
<td>coupon_id</td>
<td>Unique id for a discount coupon</td>
</tr>
<tr>
<td>customer_id</td>
<td>Unique id for a customer</td>
</tr>
</tbody>
</table>

<b> sample_submission.csv </b>: This file contains the format in which you have to submit your predictions.

To summarise the entire process:

<ul>
<li>Customers receive coupons under various campaigns and may choose to redeem it.</li>
<li>They can redeem the given coupon for any valid product for that coupon as per coupon item mapping within the duration between campaign start date and end date</li>
<li>Next, the customer will redeem the coupon for an item at the retailer store and that will reflect in the transaction table in the column coupon_discount.</li>
</ul>

# Evaluation Metric

Submissions are evaluated on area under the ROC curve between the predicted probability and the observed target.

# Public and Private Split
<ul>
<li>Test data is further randomly divided into Public (40%) and Private data (60%)</li>
<li>Your initial responses will be checked and scored on the Public data.</li>
<li>The final rankings would be based on your private score which will be published once the competition is over.</li>
</ul>

# Leaderboard

<ul>
<li><strong>[Public LB]</strong> : <strong>33rd/993 Rank</strong></li>
<li><strong>[Private LB]</strong> : <strong>60th/993 Rank</strong></li>
</ul>

# Approach

<ol>
  <li> The Final Submission was combination of Part 1 and Part 2 ensemble </li>
  <li> CatBooster with Part 2 solution had 92.76 AUC on Private LB </li>
</ol>

# Learnings 

TBC
