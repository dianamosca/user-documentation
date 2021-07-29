---
date: 2021-06-22
title: Matching Two Datasets Together
categories:
description:
type: use-case
---

## 1. Overview 

This use case explains how to use Unifyd Insights Platform to match `Shipment` data with `VIP Issues`. In this scenario, the Unifyd Insight application mirrors data from two systems. First, we use Unifyd Insights to match a `VIP Issue` with a `Shipment` record. Then, once a match is made, we update the VIP platform automatically using webhook. 

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/a4aef116c4734e608a5006ba049ca585" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## 2. Reviewing Matches 

### 2.1 Navigating to the ML Tasks 

To access the project select `Machine Learning & NLP Tasks` and then `Matching`.

[![Access-Matching-Two-Datasets-Together.png](/user-documentation/images/Access-Matching-Two-Datasets-Together.png)](/user-documentation/images/Access-Matching-Two-Datasets-Together.png)

### 2.2 Using the interface

[![Matching-Two-Datasets-Together.png](/user-documentation/images/Matching-Two-Datasets-Together.png)](/user-documentation/images/Matching-Two-Datasets-Together.png)

In the view setup the following filter:
* `View_Status = Opened`
* `Master Record`
* Records with no matches

For each record click the robot icon <img src="/user-documentation/images/android.svg" width="25" height="25"> to open the lower `Matching` panel. 

In the lower panel, select only `non master records` (the grey circle) to display only Shipment data. The Matching algorithm ranks potential matches by scores. 

The matching interface
* Highlight in yellow matching string
* When two rows match perfectly on the selected field, the application will return a score of 100%. Each difference between the master record and the degrade that score

**Read more:**
* Unifyd Matching Interface (_to add_)

### 2.3 Searching for Matches

If the interface does not return a match with a high score, you can search for the entire catalog.

### 2.4 Webhook
If you found a match, click on the green check mark to confirm it. Unifyd will automatically update `VIP` platform with the following message `TFE [Current date in MM/DD format] – Please code to supplier item # [matched supplier item number].  Thank you!`

If there are no matches, you can select one of the following webhook
* Item Not in VIP Item Catalog Yet: `TFE [Current date in MM/DD format] – This item is not available for order or shipping yet.  Thank you!`
* Match Not Wanted: `Match Not Wanted (discontinued item, another suppliers’ item, etc):  TFE [Current date in MM/DD format] – Please code to 6X.  Thank you!`
* Missing Distributor Item Details: `TFE [Current date in MM/DD format] – Please ask distributor to provide product details.  Thank you!`

We will notify you by email if the bot to update VIP failed. You can then manually process the update in VIP.


## 3. Project Set up 

This section describes how we set up the project (one-time configuration). With the following set up the script is idempotent 
* if we miss an execution, the following one will reset update the process to mirror VIP and Shipment information
* if there is an update made outside Unifyd (directly in VIP, for example), Unifyd will reflect those changes at the next update.

### 3.1 Data Pipeline Overview 

An automated script (aka bot) automates the following steps four times per day (at 9 AM, 12 PM, 2 PM, and 7 PM EST). 
* Retrieve data from the `Shipment` and `VIP` systems and perform advanced data normalization
* Update data in Unifyd **dataset** with the following settings
  * One dataset per system
  * No deduplication set up; we update each dataset entirely for two reasons:
      * To ease troubleshooting and data lineage identification. One can review the data coming from each production system as we inserted them in Unifyd
      * We manage the deduplication at the catalog level
* Apply the **Wrangle** to 
  * Convert data type
  * Create the `key` used in catalog deduplication rules (more details in the next section). 
* **Map and Upload in a unique catalog** the update to the catalog as described in the following section

 

### 3.2 Catalog Mapping Configuration

The catalog mapping is set up with the following parameters:

**Master Records**
* Data coming from `VIP` are imported as `Master`
* Data coming from the `Shipment` are imported as `Non Master`


**Deduplication Rules** 
* Data coming from `VIP` has the following `KEY = ISSUE NUMBER`
* Data coming from the `Shipment` file has the following `KEY = ITEM + DIST ID`
* The mapping use `Insert new and replace old data` using the `KEY` field


### 3.3 View Set up 

The current view is configured to review and match open items from VIP rapidly.
* Field orders
* Field size
* Hide unnecessary field
* Filter on Open and Master Record 

**Read more:** 
* [Managing the Grid](/3.%20catalog%20set%20up/Catalog-Manage-Grid/)
* View Configuration (_to add_)
