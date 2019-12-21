---
title: "MongoDB"
toc: true
toc_sticky: true
date: 2019-12-22T00:58
categories:
  - Querydsl
tags:
  - querydsl, replace
last_modified_at: 2019-12-22T00:58
----
$in
```
db.getCollection('collection_name').find({ "search_field_name" : { $in : [ "search_value1", "search_value2" ] } })
```