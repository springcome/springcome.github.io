---
title: "MongoDB-LIKE 사용"
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - mongoDB
tags:
  - mongodb
  - like
  - regex
---

# MongoDB에서 LIKE를 사용하는 방법이다
```java
String name = "aaa";
Query query = new Query();
query.addCriteria(Criteria.where("name").regex(name));
```
```sql
-- name like '%aa%'
db.getCollection('collection').find(name:/aa/)

-- name like 'aa%'
db.getCollection('collection').find(name:/^aa/)

-- name like '%aa'
db.getCollection('collection').find(name:/aa$/)
```