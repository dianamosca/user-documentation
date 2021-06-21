---
date: 2021-06-17
title: Review ML and Rule Category Suggestion
categories:
- 4. Categorization Project
description:
type: Document
---


## Overview 

The left panel of the screen display the categorization status for each record.  From left to right it contains
* check box to select a record
* Comment  <img src="/user-documentation/images/comments-solid.svg" width="25" height="25"> section
* Task  <img src="/user-documentation/images/list-solid.svg" width="25" height="25">status
* Machine Learning (ML) categorization status
* Selected Label by the user
* Rules categorization status
* Record id in the catalog

[![](/user-documentation/images/Categorization-Left-Overview.png)](/user-documentation/images/Categorization-Left-Overview.png)

## Label Status 

At the center the Label Satus (or Selected Label) indicate
*  <img src="/user-documentation/images/sitemap-solid.svg" width="25" height="25"> when a category has been set for the record
* in light green without icon when there is only 
* Click on the  <img src="/user-documentation/images/sitemap-solid.svg" width="25" height="25"> icone to see
  * The user who categorized the row
  * The category selected by the user
  * Select the  <img src="/user-documentation/images/trash-solid.svg" width="25" height="25"> trash icone to delete the category


[![](/user-documentation/images/Categorization-Label-Satus.png)](/user-documentation/images/Categorization-Label-Satus.png)


## Comment

Comment are free form text to add contextual information regarding a record or leave a note for other users. A blue comment icon <img src="/user-documentation/images/comments-solid.svg" width="25" height="25"> indicates there is one or more comment for the record. Click on the icone to open the right panel and view the comment. 

[![](/user-documentation/images/Record-Comment.png)](/user-documentation/images/Record-Comment.png)

## ML Task Status

As you start labelling records, Unifyd Insights Machine Learning will automatically starts suggesting category for similar records. The suggestion improve as more example are provided. Depending of your dataset (size and number of category), we suggest a threshold of a few hundreds to a thousand categorized rows per category for the ML to produce good recommendation. 

On the left panel the ML Suggestion returns the following information
* <img src="/user-documentation/images/android.svg" width="25" height="25"> Robot with a one green: there is only one ML suggestion for the recor
* <img src="/user-documentation/images/android.svg" width="25" height="25"> Robot with number yellow: Two ML Suggestion are conflicting. Open the `Suggested Category` panel to review the conflict 
* <img src="/user-documentation/images/android.svg" width="25" height="25"> Robot with number in red: Multiple ML Suggestion are conflicting. Open the `Suggested Category` panel to review the conflict 
* <img src="/user-documentation/images/thumbs-up-solid.svg" width="25" height="25">Green thumb up: ML Suggestion aggrees with user label
* <img src="/user-documentation/images/thumbs-down-solid.svg" width="25" height="25">Red thumb down: ML Suggestion disagrees with user label

[![](/user-documentation/images/ML-Task-Status.png)](/user-documentation/images/ML-Task-Status.png)

### Approving ML Suggestion 

ML are only suggestion. You will need to manually review and approve them by upvoting them.
* If the selected catory is wrong, you can  down vote it to select the next suggested category. 
* At any time you can bulk upvote or downvote item from the `Action` menu.
* Once categorize the `Labels` will show the classified icon: <img src="/user-documentation/images/sitemap-solid.svg" width="25" height="25">

[![](/user-documentation/images/upvote-ml-suggestion.png)](/user-documentation/images/upvote-ml-suggestion.png)

### `Suggested Category` panel

The `Suggested Category` panel let you review conflicting ML suggestion.

_to add_

## Rules Status 

On the left panel the Rules Suggestion returns the following information
* <img src="/user-documentation/images/random.svg" width="25" height="25"> Crossed Arrow with a one green: there is only one rules suggestion for the recor
* <img src="/user-documentation/images/random.svg" width="25" height="25"> Crossed Arrow with number in red: Multiples Rules Suggestion are conflicting. Open the `Suggested Rule` panel to review the conflict 
* <img src="/user-documentation/images/random.svg" width="25" height="25"> Red Exclamation mark: Too many rules conflict with a similar score. Open the `Suggested Rule` panel to review the conflict 
* <img src="/user-documentation/images/thumbs-up-solid.svg" width="25" height="25">Green thumb up: Rule Suggestion aggrees with user label
* <img src="/user-documentation/images/thumbs-down-solid.svg" width="25" height="25">Red thumb down: Rule Suggestion disagrees with user label

[![](/user-documentation/images/Categorization-Rule-Status.png)](/user-documentation/images/Categorization-Rule-Status.png)
