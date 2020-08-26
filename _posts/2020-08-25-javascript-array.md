---
title: "JavaScript, Array"
categories:
    - JavaScript
tags:
    - push()
    - pop()
    - shift()
    - unshift()
    - indexOf()
---

## 배열생성
```javascript
    const numArr = [1, 2, 3, 4, 5];
    console.log(numArr);            // [1, 2, 3, 4, 5]

    const conArr = [];
    console.log(conArr);            // []
    
```
<br />

## push(), 배열 항목 추가
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
<br />

## pop(), 배열의 마지막 항목 제거
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
<br />

## shift(), 배열의 첫번째 항목 제거
> arr.shift()

```javascript
    const numArr = [1, 2, 3, 4, 5];
    numArr.shift();
    console.log(numArr);            // [2, 3, 4, 5]

    const removeNum = numArr.shift();
    console.log(numArr);            // [3, 4, 5]

    // removeNum, 제거된 값
    console.log(removeNum)          // 2
```
<br />

## unshift(), 배열의 첫번째에 항목 추가
> arr.unshift(element1[, ...[, elementN]])

```javascript
    const numArr = [1, 2, 3];
    numArr.unshift(0);
    console.log(numArr);            // [0, 1, 2, 3]

    const arrayCount = numArr.unshift(9);
    console.log(numArr);            // [9, 0, 1, 2, 3]

    // 배열의 length
    console.log(arrayCount);        // 5
```
<br />

## indexOf(), 배열 항목의 index찾기
> indexOf(searchElement: T, fromIndex?: number): number;

```javascript
    // 찾는 값이 배열항목에 있으면 항목의 index리턴하고 없으면 -1을 리턴한다.
    const number = [1, 2, 3, 4, 5];
    const index1 = number.indexOf(4);   // 3
    const index2 = number.indexOf(6);   // -1
```