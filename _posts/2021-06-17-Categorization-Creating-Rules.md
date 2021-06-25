---
date: 2021-06-17
title: Categorization Rules Management
categories:
- 4. Categorization Project
description:
type: Document
---

## Create a Rule

In this video
* Create a filter to validate the set of records we want to apply a rule to
* Create a rule
* Filter records with the rules applied
* Identified records with conflicting rules
* View at the project level all rules and the number of records impacted. 
* Export / Import rules


<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/f07f86baeecc4cb1be9996869c9b96ea" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

<br> 

### Auto Label Record 

If you want your rules to apply the label directly, you need to select the `Auto Label Record` option during the rule creation. 

[![Image auto-label-record](/user-documentation/images/auto-label-record.png)](/user-documentation/images/auto-label-record.png)

If your rules has
* Less than 1,000 records the new label will be applied within few seconds (you can refresh the page to see them)
* More than 1,000 records, the application will trigger a background job. You can follow its progress in the job panel (see screenshot below)

[![rules-background-job.png](/user-documentation/images/rules-background-job.png)](/user-documentation/images/rules-background-job.png)

## Edit Rules

We currently do not support Rules Edition. You will need to delete the rule and recreate it with your modification.[^1]

## Delete Rules

This tutorial explains how you can delete a categorization rule. 
1. Find a Record with the rules and click the cross arrow icon
2. Click the eye icon to open the rule panel
3. Select delete

[![Image Delete_Categorization_Rule.png](/user-documentation/images/Delete_Categorization_Rule.png)](/user-documentation/images/Delete_Categorization_Rule.png)

We also recorded a quick walkthrough. 
<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/79073ba0c85f459994bcfcb0f3027b3a" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## Downloading and Uploading Rules 

This tutorial explains how you can bulk generate categorization rules in Excel before importing in into Unifyd. In our tutorial, we only use the filter `contains` on a single column. 

---
**NOTE**

The section below needs to be updated following the new Contains filter released in June 2021

---

Using the [rules-task-template.xlsx](/asset/rules-task-template.xlsx) template (line 2 and 3 are available as an example, you can delete them): 
* `name`:  Name of the rule as it will appear in Unifyd Interface
* `output`: Name of the category it should be mapped to. You need to provide the full path of the category. We recommend that you copy the value from the Unifyd interface. 
* `filters`: **do not edit this column** The Excel formula concatenates the value from column D to G to generate the filter expression for Unifyd. The formula is 
```
="{"""&D2&""""&":{"&""""&"operand"""&":["""&F2&""""&","&""""&G2&""""&","""&"0"""&","""&"0"""&"],"""&"operator"""&":"""&E2&""""&"}}"
```
Update the following columns to generate the `filters` expression
* `Data Column Used`: Which column is used for filtering. It should match the column name in Unifyd. 
* `Filter Type`: in this tutorial, we only use `CONTAINS` (in UpperCase only) 
* `Filter Variable`: the keyword to search. It can contain only one and only one keyword. Unifyd do not support array or list of search at this point; you will need to create one filter for each value
* `But Not Variable`: the keyword to exclude from the search. It can contain only one and only one keyword. Unifyd does not support an array or list of searches at this point. 

Once your rules are generated, you can copy and paste special without the formula (using `Ctrl+Alt+V` see [Office documentation](https://support.microsoft.com/en-us/office/paste-options-8ea795b0-87cd-46af-9b59-ed4d8b1669ad#ID0EAACAAA=Windows)) the columns `name` `output` `filters` to the [rules-task-template.csv](/asset/rules-task-template.csv) document and save it as csv. 

---
**Footnote**

[^1]: See Feature [UNPR-1170](https://unifyd.atlassian.net/browse/UNPR-1170)
