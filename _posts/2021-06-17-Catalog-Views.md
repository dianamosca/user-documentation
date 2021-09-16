---
date: 2021-06-17
title: Catalog Views
categories:
- 3. Catalog Set up
order_number: 2
description:
type: Document
---
##  1. What is a view 

Catalog View save the [grid configuration](/3.%20catalog%20set%20up/Catalog-Manage-Grid/) and filter into a view for a Catalog Table. Once created, the view is accessible from the Catalog and all related ML Tasks. All Catalog Table comes with a default public view which is shared with all users. 

**Known Limitations**: The view is automatically updated as you make changes to the grid parameters and filter option. This can lead to two known side effects:
1. You cannot restore a view to a previous state. You will need to reconfigure it manually
2. Since the default view is shared with all users, filter from one user will impact others. To avoid conflicts, we recommend each user create a private default view (see section `3. Recommended Settings` below). 

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/ee5e357ea2074135b5be2bcd48eb2507" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

##  2. Creating View 

* **Create New View**: You will reset all parameters from your current view and start from a blank slate
* **Copy View**: You will start the view with the same configuration as the current view you are in. 

When creating a view, select if the view is:
* **Public**: shared with others users who have access to the catalog or ML Task. 
* **Default**: You can have only one default view. It will be displayed when you login into Unifyd. Note that if you changed view during your session, the latest loaded view will be used when accessing the catalog table (or any ML task) again. 



##  3. Recommended settings

1. **Default View** At the Catalog Table creation, configure the default view as a template for other users to create their personal view. Update column size and order, row height, display images when needed, hide un-relevant columns. 
2. **Personal View** Using `Copy View`, ask each new user to create a Default Private view (i.e., non-public) 
3. **Download View** If you are using a script to download data regularly from the catalog, you can create a dedicated private view) to manage your export format. 

