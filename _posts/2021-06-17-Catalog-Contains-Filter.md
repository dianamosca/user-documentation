---
date: 2021-06-17
title: Contains Filter
categories:
- 3. Catalog Set up
order_number: 3
description:
type: Document
---

In this tutorial, we walk through the contains filter on a catalog, including usage of
* `All Of`  to search all word separated by comma (AND search)
* `Any Of` to search any word separated by comma (OR search)
* Build complex search by combining multiple string with `AND` / `OR` / `BUT NOT` operators
* Use Case Sensitive either for a specific word 

**Known limitations**
* When using a list of comma-separated words, make sure you have no space between your term.
* You need to use Case Sensitive search for multiple words[^1]
* Note that at this stage, you cannot search string that contains a comma `,` [^2]

<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/637971818?h=358517af7e&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;" title="Unifyd Insights - Contains Filter"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

---
**Footnotes**

[^1]: See ([UNPR-1103](https://unifyd.atlassian.net/browse/UNPR-1103))
[^2]: See ([UNPR-1092](https://unifyd.atlassian.net/browse/UNPR-1092))
