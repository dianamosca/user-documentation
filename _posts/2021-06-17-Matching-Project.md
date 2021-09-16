---
date: 2021-06-17
title: Matching Introduction
categories:
- 5. Matching Project
order_number: 1
description:
type: Document
---

## 1. Project Creation 

Once you selected your `Catalog` and `Catalog Table`, select `Type = Record Matching (Entity Mastering)`.

## 2. Field Configuration

[![Matching-Field-Configuration.png](/user-documentation/images/Matching-Field-Configuration.png)](/user-documentation/images/Matching-Field-Configuration.png)

Unifyd Insight Matching algorithm provides a 100 score when two rows match perfectly on the selected field. Any differences between the two rows will degrade the matching score based on


The **Column Search Boost** let you give more or less weight to a field. For example, for a string field set with `exact` match with `extremely high` bost, the model gives an extremely high penalty to the score if the two values do not exactly match. 


**Analyzers and Schema Settings** option are
* Text
   * Exact
   * Fuzzy Match
   * Fingerprint
   * Non-Exact Match
* Numeric and Date Value 
   * Numeric Decay %
