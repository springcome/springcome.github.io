---
title: "Windows 10에서 MongoDB 설치"
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - mongoDB
tags:
  - mongodb setup
  - windows10
---
뒤늦게 mongoDB를 실무에서 사용하게 되어 집에서 설치해보려고 한다.

# 다운로드
다운로드는 <a href="https://www.mongodb.com/download-center/community">여기서</a>할수있다.<br />
OS는 Windows x64 x64를 선택하고 Package는 MSI를 선택하여 다운로드 하면된다. <br /><br />
# 설치
<img src="/assets/images/mongodb/2020010901.png" /><br />
원하는 설치경로가 있다면 별도의 경로를 설정후 계속 진행한다.<br /><br />
<img src="/assets/images/mongodb/2020010902.png" /><br />
데이터와 로그가 쌓이는 경로를 확인합니다.<br /><br />
# 환경설정
윈도우키를 눌러 `환경변수`라고치면 시스템 환경 변수 편집을 찾을수있습니다.<br />
<img src="/assets/images/mongodb/2020010903.png" /><br />
환경변수를 선택해서 들어가서 시스템 변수의 path를 선택해 편집을 눌러줍니다. <br />
<img src="/assets/images/mongodb/2020010904.png" /><br />
<img src="/assets/images/mongodb/2020010906.png" /><br />
mongoDB설치경로의 bin폴더까지 추가해줍니다.<br /><br />
# 실행
`cmd` 실행하여 mongoDB설치경로의 bin폴더로 이동합니다.<br />
`mongod.exe`를 입력하여 실행할수있습니다.<br />
실행을 하면 오류를 볼수있는데 데이터가 저장될 폴더지정이 되지 않아 발생하는 오류입니다.<br />
```
mongod --dbpath "C:\database\MongoDB\db"
```
데이터가 저장될 경로를 지정하여 실행하면 됩니다.