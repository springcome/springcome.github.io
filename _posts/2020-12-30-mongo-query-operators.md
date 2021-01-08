---
title: "MongoDB Query Operators"
categories:
    - mongoDB
tags:
    - mongoDB
    - $exists
permalink: /mongoDB/
toc: true
toc_label: "Contents"
toc_icon: "cog"
---
# $exists
[MongoDB documentation ($exists)](https://docs.mongodb.com/manual/reference/operator/query/exists/)
```
// Syntax: { field: { $exists: <boolean> } }
db.inventory.find({ username: { $exists: true } })
```
field의 존재 유무를 확인할수 있다.