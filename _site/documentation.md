## Welcome to Unifyd Documentation

### 1. Introduction

URL to login: https://profitero.unifyd.io/

Video Content: How to access
* Project
* Dataset
* Wrange/Recipe
* Catalogue
* ML Task


<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/e5dcf081f900467385a8427c4c6149fd" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

### 2. Creating a project 

In this tutorial we go through the process of uploading new data into unifyd and creating a new catalogue. This is the most simple version of the workflow without duplication set up or aggregating multiple dataset together. 

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/a1a26c79964c4326935561e5ad04f875" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

#### 2.1 How to load data manually in dataset

##### 2.1.1 Using Deduplication with Dataset



### 3. Using Wrangle

#### 3.1: Creating / Reusing a Wrangle

#### 3.2: Using Facets

### 4. Creating a Catalogue

#### 4.1 How to publish to a catalogue

##### 4.1.1 Using Deduplication with Catalogue



#### 4.2 How to publish to a catalogue

##### 4.1.2 Contains Filter

In this tutorial we walk through the contains filter on a catalogue including usage of
* `All Of`  to search all word separated by comma (AND search)
* `Any Of` to search any word separated by comma (OR search)
* Build complex search by combining multiple string with `AND` / `OR` / `BUT NOT` operators
* Use Case Sensitive either for a specific word 

**Known limitations**
* When using a list of comma separated words, make sure you have no space between your term.
* You need to use Case Sensitive search to for multiple word ([UNPR-1103](https://unifyd.atlassian.net/browse/UNPR-1103))
* Note that at this stage you cannot search string that contains a comma `,` ([UNPR-1092](https://unifyd.atlassian.net/browse/UNPR-1092))

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/71d17681c7d94543ae0cb8ccb472109b" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

##### 4.2.2 Managing View

### 5.  Create a Categorization Project

#### 5.1 Interface tour Managing the ML Task Grid
In this video we see how to manage the grid appearance including
* Resize column
* Reorder column
* Sort column
* Change the row height
* Hide column
* Filter 

We also see how you can
* Export data
* Access the rules generator
* Add a comment on a record. 


<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/22d0624e46204812832b066a8f9ddb21" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

This is how you view existing filter applied and clear sorting: 

<img class="alignleft" src="/user-documentation//screenshot/Remove_sort_filter.png" width="100%"/>

[Open Image]("/user-documentation//screenshot/Remove_sort_filter.png)


#### 5.2 Setting up a categorization project

In this video we review how to
* Create a new ML Task for Categorization
* Access other Dictionnary and Category within a project
* Configure Bootstrap ML Task 
* Create a new dictionnary
* Manually categorize records

**TIPS**: 
* You can manually categorize records in bulk by selecting multiple records and calling the `Action > Categorize` menu.  
* Filter your records to find multiple records matching the same category and select all of them before selecting a category. If you want to automatically categorize all records matching those filter, you can create a rule (section 4.2)

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/90b981d4cc13425caeb17a202cc6c844" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>



#### 5.3 Creating Rules and Rules suggestion

#### 5.3.1 Overview
In this video
* Create a filter to validate the set of records we want to apply a rules to
* Create a rule
* Filter records with the rules applied
* Identified records with conflicting rules
* View at the project level all rules and the number of records impacted. 
* Export / Import rules


<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/f07f86baeecc4cb1be9996869c9b96ea" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

#### 5.3.2 Bulk Generating Rules in Excel (Export / Import)

This tutorial explain how you can bulk generate categorization rules in Excel before importing in into Unifyd. In our tutorial we only use the filter `contains` on a single column. 

Using the [rules-task-template.xlsx](/asset/rules-task-template.xlsx) template (line 2 and 3 are available as example, you can delete them): 
* `name`:  Name of the rule as it will appear in Unifyd Interface
* `output`: Name of the category it should be mapped to. You need to provide the full path of the category. We recommend that you copy the value from the Unifyd interface. 
* `filters`: **do not edit this column** The Excel formula concatenante the value from column D to G to generate the filter expression for Unifyd. The formula is 
```
="{"""&D2&""""&":{"&""""&"operand"""&":["""&F2&""""&","&""""&G2&""""&","""&"0"""&","""&"0"""&"],"""&"operator"""&":"""&E2&""""&"}}"
```
Update the following columns to generate the `filters` expression
* `Data Column Used`: Which column is used for filtering. It should match the column name in Unifyd. 
* `Filter Type`: in this tutorial we only use `CONTAINS` (in UpperCase only) 
* `Filter Variable`: the keyword to search. It can contains only one and only one keyword. Unifyd do not support array or list of search at this point, you will need to create one filter for each value
* `But Not Variable`: the keyword to exclude from the search. It can contains only one and only one keyword. Unifyd do not support array or list of search at this point. 

Once your rules generated, you can copy and use paste special without the formula (using `Ctrl+Alt+V` see [Office documentation](https://support.microsoft.com/en-us/office/paste-options-8ea795b0-87cd-46af-9b59-ed4d8b1669ad#ID0EAACAAA=Windows)) the columns `name` `output` `filters` to the [rules-task-template.csv](/asset/rules-task-template.csv) document and save it as csv. 

#### 5.3.3 Delete Categorization Rules

This tutorial explain how you can delete a categorization rules. 
1. Find a Record with the rules and click the cross arrow icone
2. Click the eye icone to open the rule panel
3. Select delete

<img class="alignleft" src="/user-documentation/screenshot/Delete_Categorization_Rule.png" width="100%"/>

[Open Image](/user-documentation/screenshot/Delete_Categorization_Rule.png)

We also recorded a quick walkthrough. 
<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/79073ba0c85f459994bcfcb0f3027b3a" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

#### 5.4 Using Task Filters

#### 5.5 Usage of disambuigiton chart


### 6.  Create a Record Matching Project