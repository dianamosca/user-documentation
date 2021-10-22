---
date: 2021-06-17
title: Categorization Rules Management
categories:
- 4. Categorization Project
order_number: 3
description:
type: Document
---

## 1. Create a Rule

In this video
* Create a filter to validate the set of records we want to apply a rule to
* Create a rule
* Filter records with the rules applied. Learn more regarding [filtering in catalog](/3.%20catalog%20set%20up/Contains-Filter/)
* Identified records with conflicting rules
* View at the project level all rules and the number of records impacted. 
* Export / Import rules


<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/637969505?h=b8f6859313&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;" title="Unifyd Insights - Create Categorization Rules"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

<br> 

### 1.1 Auto Label Record 

If you want your rules to apply the label directly, you need to select the `Auto Label Record` option during the rule creation. 

[![Image auto-label-record](/user-documentation/images/auto-label-record.png)](/user-documentation/images/auto-label-record.png)

If your rules has
* Less than 1,000 records the new label will be applied within few seconds (you can refresh the page to see them)
* More than 1,000 records, the application will trigger a background job. **The new category will appears only once the job completed** You can follow its progress in the job panel (see screenshot below)

[![rules-background-job.png](/user-documentation/images/rules-background-job.png)](/user-documentation/images/rules-background-job.png)

## 2. Edit Rules

We currently do not support Rules Edition. You will need to delete the rule and recreate it with your modification.[^1]

## 3. Delete Rules

This tutorial explains how you can delete a categorization rule. 
1. Find a Record with the rules and click the cross arrow icon
2. Click the eye icon to open the rule panel
3. Select delete

[![Image Delete_Categorization_Rule.png](/user-documentation/images/Delete_Categorization_Rule.png)](/user-documentation/images/Delete_Categorization_Rule.png)

We also recorded a quick walkthrough. 
<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/637969646?h=b650022fcb&badge=0&autopause=0&player_id=0&app_id=58479/embed" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen frameborder="0" style="position:absolute;top:0;left:0;width:100%;height:100%;"></iframe></div>

---
**Footnote**

[^1]: See Feature [UNPR-1170](https://unifyd.atlassian.net/browse/UNPR-1170)
