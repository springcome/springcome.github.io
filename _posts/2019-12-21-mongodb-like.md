---
title: "MongoDB-LIKE 사용"
toc: true
toc_sticky: true
date: 2019-12-22T00:39
categories:
  - mongoDB
tags:
  - mongodb, like, regex
last_modified_at: 2019-12-22T00:39
----

# MongoDB에서 LIKE를 사용하는 방법이다
```
String name = "aaa";
Query query = new Query();
query.addCriteria(Criteria.where("name").regex(name));
```