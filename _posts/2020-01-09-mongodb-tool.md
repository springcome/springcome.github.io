---
title: "Robo 3T 설치 (Windows 10)"
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - mongoDB
tags:
  - mongodb
  - robo3t
---
# 다운로드
<a href="https://robomongo.org/">https://robomongo.org/</a><br />
다운로드는 Robo 3T Only를 선택하여 다운로드 합니다. <br />

# 실행
설치를 완료하고 Connection을 생성합니다.<br />
<img src="/assets/images/mongodb/2020010907.png" /><br /><br />
제 PC에설치된 DB를 사용할것이므로 Address는 localhost, Port는 27017이 기본 Port이므로 아무것도 변경하지 않고 `Test`를 눌러 접속할수있는지 확인합니다.<br />
물론 PC의 DB가 실행중인 상태여야합니다.<br />
<img src="/assets/images/mongodb/2020010908.png" /><br />
<img src="/assets/images/mongodb/2020010909.png" /><br />

# 데이터베이스 생성
<img src="/assets/images/mongodb/2020010910.png" /><br />
`localhost`를 우클릭하면 Create Database메뉴를 클릭하여 Database를 생성할수 있습니다.<br /><br />

# Collection 생성
<img src="/assets/images/mongodb/2020010911.png" /><br />
Create collection을 선택하여 생성해줍니다.

# Document 추가
생성한 collection을 우클릭해보면 insert document가 있습니다.<br />
적당한 field를 추가해보도록 합니다.<br />
<img src="/assets/images/mongodb/2020010912.png" /><br />
저장후 user collection을 더블클릭하면 저장된 document를 확인할수있습니다.<br />
<img src="/assets/images/mongodb/2020010913.png" /><br />