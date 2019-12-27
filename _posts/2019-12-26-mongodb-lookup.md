---
title: "mongoDB, $lookup"
toc: true
toc_label: "Contents"
toc_icon: "cog"
date: "2019-12-26"
categories:
  - mongoDB
tags:
  - mongoDB
  - aggregate
  - lookup
---
$lookup을 사용하여 join한 효과를 얻을수 있습니다.

# 테스트 환경
> mongoDB version : 4.0.5-18
<br />사용툴 : Robo 3T - 1.3

# 테스트 데이터
>A collection
```sql
{
    "_id": ObjectId("a1"),
    "name": "a1 name"
},
{
    "_id": ObjectId("a2"),
    "name": "a2 name"
}
```

>B collection
```sql
{
    "_id": ObjectId("b1"),
    "group": [
        {
            "aid": "a1"
        }
    ]
},
{
    "_id": ObjectId("b2"),
    "group": [
        {
            "aid": "a1"
        }
    ]
},
{
    "_id": ObjectId("b3"),
    "group": [
        {
            "aid": "a2"
        }
    ]
}
```
위와같이 테스트데이터가 있다고 가정할때 내가 기대하는 결과는 다음과 같다.
```sql
{
    "_id": ObjectId("a1"),
    "name": "a1 name",
    "aGroup": [
        {
            "_id": ObjectId("b1"),
            "group": [
                {
                    "aid": "a1"
                }
            ]
        },
        {
            "_id": ObjectId("b2"),
            "group": [
                {
                    "aid": "a1"
                }
            ]
        }
    ]
},
{
    "_id": ObjectId("a2"),
    "name": "a2 name",
    "aGroup": [
        {
            "_id": ObjectId("b3"),
            "group": [
                {
                    "aid": "a2"
                }
            ]
        }
    ]
}
```

# $lookup 사용
```sql
db.a.aggregate([
    $lookup: {
        from: "b",
        localField: "_id",
        foreignField: "group.aid",
        as: "aGroup"
    }
])
```
위와같이 SQL을 작성하였을때 오류가 발생한다. localField: "_id"와 foreignField: "group.aid"의 Type이 달라 오류가 발생하는것을 볼수있을것이다.
<br/>
데이터 타입을 맞춰줄수 있는 방법은 여러가지가 있는것으로 보인다. 여러방법으로 시도하여 정상작동하는 방법을 찾을수있었다. $addFields를 사용한 방법인데 하나의 필드를 추가하고 타입을 맞춰 사용하는 방법이다.

# $addFields 사용
```sql
db.a.aggregate([
    {
        $addFields: {
            aid: { $toString: "$_id"}
        }
    },
    {
        $lookup: {
            from: "b",
            localField: "aid",
            foreignField: "group.aid",
            as: "aGroup"
        }
    }
])
```
위에서 설명했듯이 "aid"필드를 하나추가하고 ObjectId Type을 String Type으로 변경하였다.

# 구현
```java
// $addFields
AggregationOperation addFields = new AggregationOperation() {
    @Override
    public DBObject toDBObject(AggregationOperationContext aggregationOperationContext) {
        BasicDBObject addFieldsObject = new BasicDBObject();
        addFieldsObject.append("aid", new BasicDBObject("$toString", "$_id"));
        return new BasicDBObject("$addFields", addFieldsObject);
    }
};

// #lookup
LookupOperation lookupOperation = LookupOperation.newLookup()
    .from("b")
    .localField("aid")
    .foreignField("group.aid")
    .as("bData");

// Aggregation
Aggregation agg = Aggregation.newAggregation(
    addFields,
    lookupOperation
);

// Result
AggregationResults<A> results = mTemplate.aggregate(agg, "a", A.class);
List<A> list = results.getMappedResults();
```

A.class에서 aEntity를 받을수있는 변수를 선언해줘야 한다.
```java
public class A {
    private String id;
    private String name;
    private List<B> bData;
}
```
