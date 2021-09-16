---
date: 2021-06-17
title: Review ML and Rule Category Suggestion
categories:
- 4. Categorization Project
order_number: 2
description:
type: Document
---

## 1. Overview 

The left panel of the screen displays the categorization status for each record.  From left to right it contains
* Check box to select a record
* Comment section: <img src="/user-documentation/images/comments-solid.svg" width="25" height="25"> 
* Task status: <img src="/user-documentation/images/list-solid.svg" width="25" height="25">
* Machine Learning (ML) categorization status
* Selected Label by the user
* Rules categorization status
* Record id in the catalog

[![Categorization-Left-Overview.png](/user-documentation/images/Categorization-Left-Overview.png)](/user-documentation/images/Categorization-Left-Overview.png)

## 2. Label Status 

At the center, the Label Status (or Selected Label) indicates
*  <img src="/user-documentation/images/sitemap-solid.svg" width="25" height="25"> when a category has been set for the record
* In light green without icon when there is only 
* Click on the  <img src="/user-documentation/images/sitemap-solid.svg" width="25" height="25"> icon to see
  * The user who categorized the row
  * The category selected by the user
  * Select the  <img src="/user-documentation/images/trash-solid.svg" width="25" height="25"> trash icon to delete the category


[![Categorization-Label-Satus.png](/user-documentation/images/Categorization-Label-Satus.png)](/user-documentation/images/Categorization-Label-Satus.png)


## 3. Comment

Comment are free form text to add contextual information regarding a record or leave a note for other users. A blue comment icon <img src="/user-documentation/images/comments-solid.svg" width="25" height="25"> indicates there is one or more comment for the record. Click on the icon to open the right panel and view the comment. 

[![Record-Comment.png](/user-documentation/images/Record-Comment.png)](/user-documentation/images/Record-Comment.png)

## 4. ML Task Status

Unifyd Insights Machine Learning will automatically begins to suggest categories for similar records as you start labeling. The suggestion improves as you manually label more records. Depending on your dataset size and the number of categories, we suggest a threshold of a few hundred to a thousand categorized rows per category for the ML to produce a good recommendation. 

On the left panel, the ML Suggestion returns the following information:
* <img src="/user-documentation/images/android.svg" width="25" height="25"> Robot with a one green: there is only one ML suggestion for the record
* <img src="/user-documentation/images/android.svg" width="25" height="25"> Robot with number yellow: Two ML Suggestion are conflicting. Open the `Suggested Category` panel to review the conflict 
* <img src="/user-documentation/images/android.svg" width="25" height="25"> Robot with number in red: Multiple ML Suggestion are conflicting. Open the `Suggested Category` panel to review the conflict 
* <img src="/user-documentation/images/thumbs-up-solid.svg" width="25" height="25">Green thumb up: ML Suggestion aggrees with user label
* <img src="/user-documentation/images/thumbs-down-solid.svg" width="25" height="25">Red thumb down: ML Suggestion disagrees with user label

[![ML-Task-Status.png](/user-documentation/images/ML-Task-Status.png)](/user-documentation/images/ML-Task-Status.png)

### 4.1 Approving ML Suggestion 

ML recommendations are only suggestions. You will need to review and upvote (i.e. approve) them manually.
* If the selected category is wrong, you can down vote it to select the next suggested category. 
* At any time you can bulk upvote or downvote item from the `Action` menu.
* Once categorize the `Labels` will show the classified icon: <img src="/user-documentation/images/sitemap-solid.svg" width="25" height="25">

[![upvote-ml-suggestion.png](/user-documentation/images/upvote-ml-suggestion.png)](/user-documentation/images/upvote-ml-suggestion.png)

## 5. Rules Status 

On the left panel, the Rules Suggestion returns the following information:
* <img src="/user-documentation/images/random.svg" width="25" height="25"> Crossed Arrow with a one green: there is only one rules suggestion for the recor
* <img src="/user-documentation/images/random.svg" width="25" height="25"> Crossed Arrow with number in red: Multiples Rules Suggestion are conflicting. Open the `Suggested Rule` panel to review the conflict 
* <img src="/user-documentation/images/exclamation.svg" width="25" height="25"> Red Exclamation mark: Too many rules conflict with a similar score. Open the `Suggested Rule` panel to review the conflict 
* <img src="/user-documentation/images/thumbs-up-solid.svg" width="25" height="25">Green thumb up: Rule Suggestion aggrees with user label
* <img src="/user-documentation/images/thumbs-down-solid.svg" width="25" height="25">Red thumb down: Rule Suggestion disagrees with user label

[![Categorization-Rule-Status.png](/user-documentation/images/Categorization-Rule-Status.png)](/user-documentation/images/Categorization-Rule-Status.png)
