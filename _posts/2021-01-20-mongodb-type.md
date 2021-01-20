---
title: "MongoDB, $type을 사용한 null값 조회"
permalink: /mongoDB/
toc: false
toc_label: "Contents"
toc_icon: "cog"
categories:
  - mongoDB
tags:
  - mongodb
  - null
---
필드값이 null인 데이터를 조회할때 아래와 같이 하면 필드가 없는 데이터도 조회가 된다.
```sql
.find({
    "field": null
})
```

원하는 값은 필드가 존재하면서 필드의 값이 null로 들어가 있는 데이터만 조회를 하고싶다면 $type을 사용하자.
```sql
.find({
    "field": { $type: 10 }
})
```

참고<br />
<a href="https://docs.mongodb.com/manual/reference/operator/query/type/" target="_blank">monboDB - $type</a>
