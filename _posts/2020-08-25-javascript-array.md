---
title: "JavaScript, Array"
categories:
    - JavaScript
tags:
    - push()
    - pop()
---

# 배열생성
```javascript
    const numArr = [1, 2, 3, 4, 5];
    console.log(numArr);            // [1, 2, 3, 4, 5]

    const conArr = [];
    console.log(conArr);            // []
    
```

# push(), 배열 항목 추가
> arr.push(element1[, ...[, elementN]])
```javascript
    const members = [];

    members.push('A');
    console.log(members);           // ['A']

    members.push('B');
    console.log(members);           // ['A', 'B']

    const memberCount = member.push('C', 'D');
    console.log(members);           // ['A', 'B', 'C', 'D']
    console.log(memberCount);       // 항목을 추가한뒤 배열의 length
```

# pop(), 배열의 마지막 항목 제거
> arr.pop()
```javascript
    const numArr = [1, 2, 3, 4, 5];

    numArr.pop();
    console.log(numArr);            // [1, 2, 3, 4]

    numArr.pop();
    console.log(numArr);            // [1, 2, 3]

    const removeNum = numArr.pop();
    console.log(numArr);            // [1, 2]

    // removeNum, 제거된 값
    console.log(removeNum);         // 3
```