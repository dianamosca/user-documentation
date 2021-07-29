---
date: 2021-06-17
title: ID Policy and Deduplication Settings
categories:
- 1. Project & Dataset
order_number: 3
description:
type: Document

---

<div style="position: relative; padding-bottom: 57.05229793977813%; height: 0;"><iframe src="https://www.loom.com/embed/d6c7a248fd7b46e0a90929d0452a7f9d" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

When you create a dataset for the first time, you have the option to setup a ID Policy/Deduplication Settings.

**Key field**: Select the fields that will determine uniqueness of records for insertion. The field (or combination of fields) must be 
* unique per records
* always present in the dataset (not null). 

**The update parameters** are: 
* `None`: Unifyd will import the entier file for each dataset update. This setting is great if you want to keep a historical version of a records overtime across different updates.
* `Insert Only New Records`: If the record has already been uploaded in previous dataset update, it will be discarded from the newest file update. You will see a lower amount of records inserted in Unifyd compare to the total count in your file. New records are inserted. 
* `Insert and Update Records`: If the record has already been uploaded in previous dataset update, the data in the previous dataset will be updated. In other word we will not keep historical version of a record, the entire dataset only contains the most recent version of each record. The updated record will also be present in the latest dataset update. New records are inserted. 


