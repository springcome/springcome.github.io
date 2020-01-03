---
title: "MongoDB"
permalink: /mongoDB/
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - mongoDB
tags:
  - mongodb
  - in
---
# $in
```java
db.getCollection('collection_name').find({ "search_field_name" : { $in : [ "search_value1", "search_value2" ] } })
```
