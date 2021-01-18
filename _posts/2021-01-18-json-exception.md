---
title: "Exception, com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException: Unrecognized field"
permalink: /Exception/
toc: false
toc_label: "Contents"
toc_icon: "cog"
categories:
  - Exception
tags:
  - UnrecognizedPropertyException
  - json
---
아래와 같이 json파일을 읽어 Entity 클래스에 바인드시킬때 오류가 발생
```java
ObjectMapper mapper = new ObjectMapper();
Entity entity = mapper.readValue(ResourceUtils.getFile("classpath:data/test.json"), new TypeReference<>(){});
```

```
com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException: Unrecognized field
not marked as ignorable
```

Json 데이터에는 있지만 Entity에는 없는 property가 없어 데이터를 바인딩 할수 없을때 발생한다.

아래와 같이 설정을 추가하면 된다.
```java
ObjectMapper mapper = new ObjectMapper();
mapper.configure(DeserializationFeature.FAIL_ON_UNKNOWN_PROPERTIES, false);
```
