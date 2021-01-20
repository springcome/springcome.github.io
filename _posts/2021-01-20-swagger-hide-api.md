---
title: "Swagger, api 숨기기"
permalink: /Java/
toc: false
toc_label: "Contents"
toc_icon: "cog"
categories:
  - Java
tags:
  - hide api
---
API중에 외부에 노출시키고 싶지 않은 API는 숨길수 있다.
```java
@Api(hidden = true)
```

하지만 현재 이 속성은 작동하지 않고 있고 아래와 같이 사용하여 원하는 작업을 할수 있다.
```java
@ApiIgnore
```

<a href="https://github.com/springfox/springfox/issues/2437" target="_blank">Github</a>에서도 다뤄진 내용이므로 참고.
