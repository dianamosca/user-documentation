---
date: 2021-06-17
title: Categorization Download Label
categories:
- 4. Categorization Project
order_number: 4
description:
type: Document
---

## 1. Download the categorization Label 

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/fb038906378b44898d5ad2db8c9a5a8f" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>


## 2. Export file format 

The export file will contain all the columns from your view plus the following extra columns.

### 2.1 Catalog

The following fields contain the records metadata: 
* `Record ID`: the unique id of the record in the dataset.
* `Task Id`: the unique id of the task in Unifyd Insight
* `Catalog Id`: the unique id of the catalog in Unifyd Insight
* `Catalog Name`: the name of the catalog in Unifyd Insight

### 2.2 Expert Labelling

The export file contains only the selected label for the record[^1]. The following fields are available: 
* `Approved`: boolean - if the label has been approved in Unifyd Application
* `Expert Label`: Name of the **Label** set by the expert. The field is empty if no Expert has categorized the record. 
* `Expert`: Expert user name

### 2.3 ML Labelling

The export file contains only the highest score ML recommendation for the record[^1].a
* `ML Label`: Name of the **Label** set by the ML task. This will be present 
* `ML Label Score`: Score of the label 

### 2.4 Rule Labelling

The export file contains only the value of the highest score rule for the record[^1]. 
* `Rule Label`: Name of the **Label** set by the rule. The field will be empty if no rules apply to the record. 
* `Rule Name`: Name of the rule
* `Rules`: Multi-value field, comma-separated


## 3. Selecting labels

As you review the results, you will need to select the best label for each record. We recommend the following naive model:
* Select the `Expert Label` by default
* If `Expert Label` is blank, select the `Rule Label`
* If the `Rule Label` is blank, select the `ML Label`


---
**Footnotes**

[^1]: We can prepare a custom export with all the expert labeling, rules, and ML suggestion for a record. Contact us for more details. 
