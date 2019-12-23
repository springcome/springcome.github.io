---
title: "Vue, TypeError: cannot read property '' of undefined"
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - Vue
tags:
  - vue
  - error
  - undefined
---
# 오류발생 코드
```javascript
data() {
    return {
        group: {
            options: []
            , select: []
        }
    }
},
methods: {
    aMethod() {
        this.group.select.forEach(function(value) {
            this.bMethod(value);
        });
    },
    bMethod(select) {
        console.log(select);
    }
}
```
# 오류코드 확인
> TypeError: Cannot read property '' of undefined

aMethod를 호출할때 위와 같은 오류가 발생.

```javascript
    this.bMethod(value);
```
bMethod를 호출하는 부분에서 오류가 발생하는 것을 확인.

오류를 확인하기 위해 aMethod의 forEach문이 시작하기전
console.log(this); 그리고 forEach문 안에서 console.log(this); 를 출력하도록 하였다.

forEach 시작전의 this 출력 : [object Object]
forEach 안쪽의 this 출력 : undefined

forEach 안쪽에서는 this를 읽지 못하는것안 확인.

# 해결방법
forEach문에 this를 bind해줌으로서 문제 해결
```javascript
    aMethod() {
        this.group.select.forEach(function(value) {
            this.bMethod(value);
        }, this);
    }
```
또는
```javascript
    aMethod() {
        this.group.select.forEach(function(value) {
            this.bMethod(value);
        }.bind(this));
    }
```

# 참고
<a href="https://stackoverflow.com/questions/43724426/this-is-undefined-inside-the-foreach-loop" _blank>https://stackoverflow.com/questions/43724426/this-is-undefined-inside-the-foreach-loop</a>
