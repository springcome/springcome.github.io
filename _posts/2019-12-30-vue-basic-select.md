---
title: "Vue, <select />에 대한 사용"
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - Vue
tags:
  - vue
  - select
  - selected
---
<strong>학습을 하면서 추가되는 내용은 지속적으로 업데이트 할 예정입니다.</strong>

# :options
> select box의 option항목을 binding합니다.
보통 select box의 option항목은 for문을 사용하여 추가하여 사용했지만 아래와 같이 사용할수 있습니다.
```html
<select
    :options="statusOptions"></select>
```
```javascript
data() {
    return {
        statusOptions: [
            { value: 1, text: 'option1' },
            { value: 2, text: 'option2' }
        ]
    }
}
```
>:options 속성을 사용하여 option으로 사용될 데이터를 binding할수 있습니다.

# selected (v-model)
> select box의 선택값을 지정합니다.
select box의 option을 선택하거 조회한 데이터를 가지고 select box의 특정 option을 선택하고 싶을때 사용합니다.
```html
<select
    v-model="status"></select>
```
```javascript
data() {
    return {
        status: ''
    },
    created() {
        this.status = 2;
    }
}
```
>- 사용자가 select box의 option을 선택하면 status의 값이 업데이트 됩니다.
>- 조회된 status의 값이 2라고 가정하고 status의 값을 업데이트 하면 selected한 상태가 됩니다.
