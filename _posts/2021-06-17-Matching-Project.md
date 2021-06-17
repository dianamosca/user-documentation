---
date: 2021-06-17
title: Matching Introduction
categories:
- 5. Matching Project
description:
type: Document
---

## Project Creation 

Once you selected your `Catalog` and `Catalog Table`, select `Type = Record Matching (Entity Mastering)`

## Field Configuration

<img class="alignleft" src="/user-documentation/images/Matching-Field-Configuration.png" width="100%"/>

Unifyd Insight Matching algorithm provide an 100 score when two rows matches perfectly on the selected field. Any differences between the two rows will degrade the matching score based on


The **Column Search Boost** let you give more or less weight to a field. Matching (or non matching) results  - For example for a string field set with `extact` with `extremly high` boot, the model gives an extremely high penalty to the score if the two value does not exactly match. 


**Analyzers and Schema Settings** option are
* Text
   * Exact
   * Fuzzy Match
   * Fingerprint
   * Non Exact Match
* Numeric and Date Value 
   * Numeric Decay %
 


