---
title: "Querydsl, replace"
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - Querydsl
tags:
  - querydsl, replace
---

# Replace SQL
column_name의 값의 공백을 제거하여 'aaa'와 동일한 데이터를 조회
```sql
SELECT *
FROM table
WHERE replace(column_name, ' ', '') = 'aaa'
```

# Querydsl
```java
StringExpression se = StringTemplate.create("replace({0}, ' ', '')", column_name);
return select().from(table).where(
            se.eq('aaa')
        ).list(table);
```
