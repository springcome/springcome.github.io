---
title: "Android, Event for handling the focus of the EditText"
categories:
    - Android
tags:
    - android
    - EditText
    - focus event
permalink: /Android/
toc: false
toc_label: "Contents"
toc_icon: "cog"
---
EditText의 focus in/out에 대한 이벤트를 처리할수있다.
```java
editText.setOnFocusChangeListener(new View.OnFocuschangeListener() {
    @Override
    public void onFocusChange(View v, boolean hasFocus) {
        if (hasFocus) {
            // focus in
        } else {
            // focus out
        }
    }
});
```