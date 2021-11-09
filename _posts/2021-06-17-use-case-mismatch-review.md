---
date: 2021-06-22
title: MisMatch Review
categories:
description:
type: use-case
---

## 1. Overview 

This use case explains how to use Unifyd Insights Platform to detect mismatches in VIP Cross Reference file.

Log in to Unifyd and navigate to the catalog `MisMatch with Priority` to review the data.

### 1.1 Review Item by Priority. 

You can **review items by priority**, at the beginning of the project or when you want to clear older potential mismatches detected by Unifyd. 

To do so, use the filter to select:
* List of `Review Priority` to select the level of priority you like to review. 
* `Review Status` is `(blank)` to focus on items you have not reviewed yet. 

When you review an item, update the `Review Priority` field to track your progress. In your comment, you can add the `Count False` and `C_Desc_Score`. It will help to see if there are changes when the records are updated. 

### 1.2 Review Recent Items 

After each update, **review recent items** to focus on active sales and ensure the `Review Status` set previously is still current. 

To do so, use the filter to select:
* Records recently updated using the `Last Updated`
* List of `Review Priority` 
* Compare the `Count False` and `C_Desc_Score` in the `Review Status` notes and compare it with the field value.
* Edit the `Review Status` with your notes and the current  `Count False` and `C_Desc_Score`. 
* The `History` tab list all the edits made to the `Review Status` field.
 

## 2. Fields Comparison

Unifyd compares the following fields to detect a mismatch. 
* `Dist. Selling Unit` vs. `Supp. Selling Units` returns a boolean
* `Dist. U/C` vs. `Supp. U/C` returns a boolean
* `Supp GTIN` vs. `Dist GTIN` returns a boolean
* `Dist Item Size` vs. `Package` returns a boolean
* Normalized `Vintage` field vs. vintage extracted from `Supp Item Description` returns a boolean
* `Dist Item Desc` vs. `Supp Item Desc` return a match probability. The lower the score, the more risk of mismatch. The results is stored in the field `C_Desc_Score`.

The system does not compare if one of the fields is null.  The first boolean are summarized in the `Count False`. 

## 3. Priority Computation 

Using the four following fields we compute the review priority for each field 
* `Active`
* `Last Updated`
* `Count False` 
* `C_Desc_Score`

### 3.1 High Priority

All High Priority records are `Active` and have a `Last_Updated` value in the last 20 weeks from today and either
* 4 or more `Count False`  <br>
[![High-Count.png](/user-documentation/images/mismatch/High-Count.png)](/user-documentation/images/mismatch/High-Count.png)

* a `C_Desc_Score` lower than 20. <br> 
[![High-Score.png](/user-documentation/images/mismatch/High-Score.png)](/user-documentation/images/mismatch/High-Score.png)


### 3.2 Medium Priority

All Medium Priority records are `Active`
* 3 `Count False` and a `Last Updated` less than 50 weeks. 
* 4 or more `Count False` and a `Last Updated` between 20 and 50 weeks from today <br>
[![Medium-Count.png](/user-documentation/images/mismatch/Medium-Count.png)](/user-documentation/images/mismatch/Medium-Count.png)

* a `C_Desc_Score` lower than 20 and a `Last Updated` between 20 and 50 weeks from today  <br> 
[![Medium-Score.png](/user-documentation/images/mismatch/Medium-Score.png)](/user-documentation/images/mismatch/Medium-Score.png)

### 3.3 Low Priority

All Low Priority records are `Active` without any filter on the `Last Updated` field with either
* A score under 20 and a `Last Updated` over  50 weeks from today
* 1 or more `Count False` that are not already High or Medium priority<br>
[![Low-Count.png](/user-documentation/images/mismatch/Low-Count.png)](/user-documentation/images/mismatch/Low-Count.png)







