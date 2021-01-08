---
title: "Android, ImageView에서 이벤트가 발생하는 영역 조정"
categories:
    - Android
tags:
    - android
    - ImageView
permalink: /Android/
toc: false
toc_label: "Contents"
toc_icon: "cog"
---
```xml
<ImageView
    android:src = "@drawable/icon"
    android:layout_width="24dp"
    android:layout_height="24dp"
/>
위와같이 코드를 작성하고 터치하여 이벤트가 발생하도록 onClick 이벤트를 걸어주었는데, 이미지가 작아서 그런지 여러번 터치를 해야지만 (정확한 위치를) 이벤트가 발생해 이벤트가 발생하는 영역을 조정할 필요가 하다.
```