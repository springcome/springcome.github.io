---
title: "MongoDB"
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - Querydsl
tags:
  - querydsl, replace
----
$in
```
db.getCollection('collection_name').find({ "search_field_name" : { $in : [ "search_value1", "search_value2" ] } })
```