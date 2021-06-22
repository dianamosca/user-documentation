---
date: 2021-06-22
title: Matching Two Datasets Together
categories:
description:
type: use-case
---

This use case explain how to use Unifyd Insights Platform to match `Shipment` data with `VIP Issues`. In this scenario Unifyd Insight application mirror data from two systems. We use Unifyd Insights to perform identify `Shipment` records matching a `VIP Issue`. Once the match perform, the data is automatically pushed using webhook into the operation system. 

## Project Set up 

This section describes how we set up the project (one time configuration). With the following set up the script is idempotent 
* if we miss an execution, the following one will reset update the process to mirror VIP and Shipment information
* if there is update made outside Unifyd (directly in VIP for example), Unifyd will reflect those changes at the next update.

### Data Pipeline Overview 

A automated script (aka bot) automates the following steps four times per day (at 9AM, 12PM, 2PM and 7PM EST). 
* Retrive data from the `Shipment` and `VIP` systems and perform advanced data normalization
* Update data in Unifyd **dataset** with the following settings
  * One dataset per system
  * No deduplication set up, we update each dataset in full for two reasons
      * Ease troubleshooting and data lineage identification. One can review the data as they were inserted in Unifyd
      * We manage the deduplication at the catalog level
* Apply the **Wrangle** to 
  * Convert data type
  * Create the `key` used in catalog deduplication rules (see following section). 
* **Map and Upload in a commom catalog** the update to the catatalog as described in the following section

 

### Catalog Mapping Configuration

The catalog mapping is set up with the following parameters:

**Master Records**
* Data coming from `VIP` are imported as `Master`
* Data coming from the `Shipment` are imported as `Non Master`


**Deduplication Rules** 
* Data coming from `VIP` has the following `KEY = ISSUE NUMBER`
* Data coming from the `Shipment` file has the following `KEY = ITEM + DIST IT`
* The mapping use `Insert new and replace old data` using the `KEY` field


### View Set up 

The current view is configured with optimized
* Field orders
* Field size
* Hide unecessary field
* Filter on Open and Master Record 

Read more on 
* [Managing the Grid](/3.%20catalog%20set%20up/Manage-Catalog-Grid/)
* View Configuration (_to add_)

## Reviewing Matches 

### Using the interface

[![](/user-documentation/images/Matching-Two-Datasets-Together.png)](/user-documentation/images/Matching-Two-Datasets-Together.png)

In the view setup the following filter:
* `View_Status = Opened`
* `Master Record`
* Records with no matches

For each record click the robot icon <img src="/user-documentation/images/android.svg" width="25" height="25"> to open the lower `Matching` panel. 

In the lower panel select only `non master records` (the grey circle) to display only Shipment data. The Matching algorythme ranks potential matches by scores. 

The matching interface
* Highlight in yellow matching string
* When two rows matches perfectly on the selected field the application will return a score of 100%. Each difference between the master record and the degrade that score

Read more:
* Unifyd Matching Interface (_to add_)

### Searching for Matches

If the interface does not return a match with a high score you can search for the entire catalog.

### Webhook
If you found a match, click on the green check mark to confirm it. Unifyd will automaticall update `VIP` platform with the following message `TFE [Current date in MM/DD format] – Please code to supplier item # [matched supplier item number].  Thank you!`

If there is no matches you can select one of the following webhook
* Item Not in VIP Item Catalog Yet: `TFE [Current date in MM/DD format] – This item is not available for order or shipping  yet.  Thank you!`
* Match Not Wanted: `Match Not Wanted (discontinued item, another suppliers’ item, etc):  TFE [Current date in MM/DD format] – Please code to 6X.  Thank you!`
* Missing Distributor Item Details: `TFE [Current date in MM/DD format] – Please ask distributor to provide product details.  Thank you!`

We will notify you by email if the bot to update VIP failed. You can then manually process the update in VIP.



