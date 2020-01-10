---
title: "Vue, 유효성 검사"
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - Vue
tags:
  - vue
  - javascript
  - email
  - validation
---
# 이메일 유효성 체크 정규식
>Html
```html
<b-form-input type="email" :state="emailValidation"></b-form-input>
```

>Script
```javascript
computed: {
    emailValidation() {
        let re = /^([\w-]+(?:\.[\w-]+)*)@((?:[\w-]+\.)*\w[\w-]{0,66})\.([a-z]{2,6}(?:\.[a-z]{2})?)$/i;
        return re.test(this.userItems.id);
    }
}
```
