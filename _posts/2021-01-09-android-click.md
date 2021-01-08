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
아래와 같이 코드를 작성하고 터치하여 이벤트가 발생하도록 onClick 이벤트를 걸어주었는데, 이미지가 작아서 그런지 여러번 터치를 해야지만 (정확한 위치를) 이벤트가 발생해 이벤트가 발생하는 영역을 조정할 필요가 하다.
```xml
<ImageView
    android:src = "@drawable/icon"
    android:layout_width="24dp"
    android:layout_height="24dp"
    android:layout_marginTop="16dp"
    android:layout_marginLeft="16dp"
/>
```


# 해결방법
몇번 테스트를 진행한 결과 margin을 준영역은 이벤트가 발생하지 않는 것을 확인했고, padding은 이벤트가 발생하는것을 확인했다.
```xml
<ImageView
    android:src = "@drawable/icon"
    android:layout_width="24dp"
    android:layout_height="24dp"
    android:padding="16dp"
/>
```