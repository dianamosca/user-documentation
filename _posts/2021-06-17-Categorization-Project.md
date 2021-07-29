---
date: 2021-06-17
title: Categorization Create Project
categories:
- 4. Categorization Project
order_number: 1
description:
type: Document
---


## 1. Introduction 

We use a categorization project to assign records in a catalog to a specific category (for example, product category). Unifyd Insight human in the loop interface mix three approaches to ensure high accuracy of the categorization:
* Rules (created by domain expert)
* Machine Learning suggestion and categorization. 
* Manual categorization to 
  * Assign a record in a category and train the ML model
  * Distribute categorization task across a crowd to review Machine Learning suggestions and resolve conflicts between rules, expert and ML suggestions. 

Usually, a project is done in three phases (described on this page)
1. Project Creation
2. Training the model
3. Running the ML Task and reviewing the results. 

## 2. Creating a project 

In this video, we review how to
* Create a new ML Task for Categorization
* Configure Bootstrap ML Task 
* Create a new categorization structure
* Manually categorize records

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/90b981d4cc13425caeb17a202cc6c844" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
<br>
We review the meaning of each icon in the left menu on the page [Review ML and Rule Category Suggestion](/4.%20categorization%20project/Categorization-Review-Suggestion/)

## 3. Training the Model

Once you created your ML Task project and your category, you can start categorizing! <br>

**The goal is to categorize between at least 100 up to 1,000 items per category to train our ML model. At this stage, we will privilege various patterns for each category** (versus looking only for similar records).

* **Manually**: You can manually categorize records in bulk by selecting multiple records and calling the `Action > Categorize` menu. 
* **Using Rules**: If you want to automatically categorize all records matching a set of filters, you can create a rule. With the `Auto Label Record` option, the records will be assigned to the right category. **Learn more about [rules creation and management](4.%20categorization%20project/Categorization-Creating-Rules/)**
* **Unifyd bootstrapped Machine Learning** engine will start suggesting categories as you categorize items. Those categories are generated on the fly and are updated as you progress in your categorization. 
* The **Rules Conflict Ambiguity Chart** presents where rules and manual categorization by an expert conflict help to focus on attention. 

**Note:** If you have a similar dataset already categorized, we can leverage them as examples in the Unifyd engine. Contact us for more details. 

## 4. Running the ML Task 

Once the model is trained, we can configure a batch ML Categorization. In this process we:
* Configure the model (please get in touch with your service team for this step)
* Train the model on your dataset and batch categorize records. This task can take from few minutes to several hours, depending on the size of your dataset
* Review the conflict between ML suggestion and your rules and expert categorization. The ambiguity chart helps to target hard-to-categorize items and improve the model accuracy. 
* Build, train and rerun a new model. We usually need a couple of iteration to achieve up to 99% accuracy of the model. 
