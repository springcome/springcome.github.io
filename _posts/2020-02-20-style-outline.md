---
title: "Outline 표시 안되도록 하는 방법"
categories:
  - Style
tags:
  - style
  - outline
---
화면 UI를 작업하면서 Container, Form... 등등 사용할때 마우스로 선택한 Layout의 테두리가 표시되는 현상이 나타났다.
<br /><br/>
의도치 않게 눈에 보인것이지만 한번 눈의 띄기 시작하니 눈에 계속 거슬린다.
<br />
Global로 적용되는 Style에 아래외 같이 작성하여 해결하였다. 전체에 적용되는 Style이므로 주의해서 적용해야한다. 
<br />
```css
:focus {
    outline: none;
}
```