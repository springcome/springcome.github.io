---
title: "Atom, Github 프로젝트 연동 방법"
date: 2020-01-07 화요일 09:56:10
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - Ide
tags:
  - atom
  - github
  - clone
---
<img src="/assets/images/ide/atom/atom_log.png" />

Atom에서 git-plus Package를 사용하여 Github 의 프로젝트를 `clone`하는 방법을 설명합니다.
이미 Github에 생성된 프로젝트가 있다고 가정합니다.

# git-plus Package 설치
<img src="/assets/images/ide/atom/github01.png" />
Atom을 처음 설치하면 Welcome Guide화면을 볼수있는데 여기서 Install a Package를 선택합니다.

> 메뉴로 이동하는 방법은 Atom / Perferences / Install

<img src="/assets/images/ide/atom/github03.png" />
git-plus package를 검색해서 install 합니다.
<br /><br />
git-plus package를 설치하면 단축기를 사용하여 git 명령어를 처리할수 있습니다.
<br />단축키는 OS별로 다른걸로 생각됩니다.
<img src="/assets/images/ide/atom/github04.png" />
처음에 보았던 Welcome Guide 파일을 보면 단축키에 대한 설명이 나오니 참고하면 됩니다.

# Github project clone
원격 저장소 프로젝트의 주소를 복사합니다.
<img src="/assets/images/ide/atom/github07.png" /><br /><br />

다시 Atom으로 돌아와 단축키를 사용하여 command palette를 열어줍니다.
<img src="/assets/images/ide/atom/github05.png" />
GitHub: Clone을 선택해줍니다.<br /><br />

이제 복사해둔 주소를 넣어주면 됩니다.
<img src="/assets/images/ide/atom/github08.png" />
그리고 Clone을 버튼을 눌러 원격저장소에서 파일을 내려받습니다.
