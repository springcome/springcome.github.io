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
```sql
-- select * from user where name in ('a', 'b')
-- 대소문자 구분해야함
db.getCollection('user').find({name: {$in: ['a', 'b']}})
```
```java
String [] names = {"a", "b"};
new Query().addCriteria(Criteria.where("name").in(names));
```
