---
title: "VSCODE, Spring boot 환결 설정"
categories:
    - Ide
tags:
    - VSCODE
---
> VSCODE에서 spring boot 개발 환경 설정을 하면서 발생한 문제에 대해 정리한다. <br />
> [플러그인 설치](https://code.visualstudio.com/docs/java/java-spring-boot) <br />
>> Spring Boot Tools <br />
>> Spring Initializr <br />
>> Spring Boot Dashboard <br />

## java.home path 설정
### path 설정 위치 (맥기준) <br />
Code > Preferences > Settings 으로 이동해서 jdk를 겁색합니다. <br />
<img src="/assets/images/ide/vscode/20200826-001.png"><br />
Edit in settings.json을 선택하여 path를 입력합니다. <br />
<br />
### Mac에서 JDK 위치 찾기
JDK는 " /Library/Java/JavaVirtualMachines/jdk1.8.x_xxx.jdk/Contents/Home " 에 위치해있습니다.<br />
<br />
### pom.xml JDK version
spring boot build할때 JDK 버전문제로 오류가 발생할수 있다.<br />
설치된 JDK버전과 pom.xml의 java version을 맞춰줘야 한다.<br />
<img src="/assets/images/ide/vscode/20200826-002.png"><br />