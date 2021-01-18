---
title: "MongoDB, 필드를 제거하는 방법"
permalink: /mongoDB/
toc: false
toc_label: "Contents"
toc_icon: "cog"
categories:
  - mongoDB
tags:
  - mongodb
  - unset
---
```sql
{
    title: 'How to remove field in MongoDB'
    comment: [
        id: 'a',
        name: 'A'
    ]
}
```

위와같은 document가 있을때 comment field를 완전히 제거하는 방법.

SQL 사용
```sql
db.test.update(
    {_id: ObjectId("")},            -- 조건
    { $unset: {comment: ""}}        -- 제거 field
)
```

Code 사용
```java
Query query = new Query();
query.addCriteria(Criteria.where("_id").is(id));        // 조건

Update update = new Update();
update.unset("comment");                                // 제거 field
mongoTemplate.updateFirst(query, update, "test")
```

update를 사용할때는 unset을 사용하여 제거하고자하는 field를 지정하면 된다.
