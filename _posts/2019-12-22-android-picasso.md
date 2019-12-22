---
title: "Android, 이미지 다운로드 및 캐싱 라이브러리"
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - Android
tags:
  - android
  - image
  - picasso
---
Picasso를 사용하여 간편하게 이미지를 로딩합니다.

# dependencies 추가
```
// build.gradle 추가내용
dependencies {
    implementation 'com.squareup.picasso:picasso:2.71828'
}
```

# 사용법
```
Picasso.get().load("http://i.imgur.com/DvpvklR.png").into(imageView);
```

# 참고
Site - <a href="https://square.github.io/picasso/" _blank>https://square.github.io/picasso/</a><br />
Last version - <a href="https://github.com/square/picasso" _blank>https://github.com/square/picasso</a>