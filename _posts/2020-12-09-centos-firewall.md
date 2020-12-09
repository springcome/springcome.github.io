---
title: "CentOS 7 방화벽 포트"
categories:
    - Linux
tags:
    - linux
    - firewall
---
# firewall-cmd 설치

```
// install
[root@~]$ yum install -y firewalld

// firewalld 시작 / 등록
[root@~]$ systemctl unmask firewalld
[root@~]$ systemctl enable firewalld
[root@~]$ systemctl start firewalld
```
# 열려있는 포트 확인

```
// -t TCP
// -n 10진수 표기
// -l Listening (열려있는 상태)
// -p 상제정보
[root@~]$ netstat -tnlp
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN
tcp        0      0 127.0.0.1:25            0.0.0.0:*               LISTEN
tcp        0      0 0.0.0.0:111             0.0.0.0:*               LISTEN
tcp6       0      0 :::22                   :::*                    LISTEN
```
# 방화벽 설정 확인
```
[root@~]$ firewall-cmd --list-all
```

# 포트 열기
```
// 오픈할 포트 추가
[root@~]$ firewall-cmd --permanent --zone=public --add-port=8080/tcp
// 방화벽 설정 reload
[root@~]$ firewall-cmd --reload
```

# 포트 닫기
```
// 막을 포트 지정
[root@~]$ firewall-cmd --permanent --zone=public --remove-port=8080/tcp

// 방화벽 설정 reload
[root@~]$ firewall-cmd --reload
```
# local(외부)에서 포트가 열렸는지 확인하는 방법
```
// nc -z IP PORT
[local@~]$ nc -z 0.0.0.0 8080
// 접근이 안되면 아무 반응이 없지만 접근가능한 상태에서는 다음 메시지가 표시된다.
Connection to 0.0.0.0 port 8080 [tcp/*] succeeded!
```

> 
