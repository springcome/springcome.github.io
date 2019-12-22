---
title: "Android, ImageView를 사용한 toggle기능 사용"
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - Android
tags:
  - android
  - toggle
  - button
---

ImageView를 선택할때마다 이미지를 바꿔주어 toggle기능을 할수 있도록 한다.

속이 비어있는 별모양과 꽉찬 별모양을 준비하여 기본은 비어있고 선택시 꽉찬 별모양으로 변경되어 현재 보고 있는 content를 즐겨찾기 했다는 것을 의미하도록 할것입니다.

# 터치 이벤트가 발생했을때 상태값에 따라 이미지를 변경해주는 selector를 생성한다.
```xml
// res/drawable/selector.xml
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item
        android:state_activated="true"
        android:drawable="@drawable/ic_star_24dp" />
    <item
        android:drawable="@drawable/ic_star_border_24dp" />
</selector>
```
default로 선택되는 아이템의 상태값(속이 비어있는 별)을 true로 해준다.

# ImageView를 그려준다.
```java
<ImageView
    android:src="@drawable/selector"
    ...
    ... />
```
위에서 생성한 selector를 ImageView에 사용하도록 한다.

# ImageView의 onClick이벤트 처리
```java
star.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(final View view) {
        view.setActivated(!view.isActivated());
    }
});
```
터치 이벤트가 발생할때마다 selector의 상태값을 반대로 변경해 주도록 한다.
