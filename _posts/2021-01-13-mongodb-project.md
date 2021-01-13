---
title: "MongoDB, 원하는 필드만 조회하고 싶을때"
permalink: /mongoDB/
toc: false
toc_label: "Contents"
toc_icon: "cog"
categories:
  - mongoDB
tags:
  - mongodb
  - project
---
```sql
SELECT o.name, o.age FROM user o
WHERE o.id = 1
ORDER BY o.age ASC
```
위와같이 원하는 컬럼의 값만 조회하고 싶을때

```sql
db.getCollection('user').find({
    "id": "1"
}, {
    "name": 1, "age": 1 
}).sort({
    "age": 1
})
```
조건문 뒤에 붙여 써주면 된다.
