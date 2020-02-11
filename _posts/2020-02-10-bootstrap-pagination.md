---
title: "Bootstrap, pagination custom style"
categories:
  - Style
tags:
  - bootstrap
  - style
  - pagination
---
# 정보
vue-bootstrap을 사용하여 UI 개발중 페이징 스타일 변경요구가 발생하여 적용한 내용을 기록 합니다.

# 방법
저는 모튼 페이지에서 사용하는 페이징 스타일을 변경할것이므로 Global하게 적용되는 .css파일에 추가 하였습니다.

변경한부분<br />
    - font color</br>
    - background color

```css
/* 이동가능한 링크의 background color 와 font color */
.page-link {
    position: relative;
    display: block;
    padding: 0.5rem 0.75rem;
    margin-left: -1px;
    line-height: 1.25;
    color: #c5cfd8;
    background-color: #0068c4;
}
/* 이동할수 없는 링크의 background color 와 font color */
.page-item.disabled .page-link {
    color: #c5cfd8;
    pointer-events: none;
    cursor: auto;
    background-color: #003b7d;
}
/* 활성화 되어 있는 링크의 background color 와 font color */
.page-item.active .page-link {
    z-index: 1;
    color: #c5cfd8;
    background-color: #0089f1;
}
/* Focus되었을때의 background color 와 font color */
.page-link:focus, .page-link:hover {
    color: #c5cfd8;
    text-decoration: none;
    background-color: #0089f1;
}
```