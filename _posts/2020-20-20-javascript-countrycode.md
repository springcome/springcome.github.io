---
title: "Javascript, 국가코드 확인"
categories:
  - JavaScript
tags:
  - country code
---
Javascript를 사용해 접속한 사용자의 국가코드를 알아내는 코드입니다.
```javascript
    var type = navigator.appName;
    if (type == 'Netscape') {
        var lang = navigator.language;
    } else {
        var lang = navigator.userLanguage;
    }

    console.log(lang);
    // out : ko-KR
    
    var country_code = lang.substr(0, 2);
    console.log(country_code);
    // out : ko
```
