---
layout: "post"
title: "Querydsl, replace"
toc: true
toc_sticky: true
date: 2019-12-22T00:58
categories:
  - Querydsl
tags:
  - querydsl, replace
last_modified_at: 2019-12-22T00:58
----

# Replace SQL
column_name의 값의 공백을 제거하여 'aaa'와 동일한 데이터를 조회
```
SELECT *
FROM table
WHERE replace(column_name, ' ', '') = 'aaa'
```

# Querydsl
```
StringExpression se = StringTemplate.create("replace({0}, ' ', '')", column_name);
return select().from(table).where(
            se.eq('aaa')
        ).list(table);
```