---
title: "Vue, props에 대한 사용"
toc: true
toc_label: "Contents"
toc_icon: "cog"
categories:
  - Vue
tags:
  - vue
  - props
---
<strong>학습을 하면서 추가되는 내용은 지속적으로 업데이트 할 예정입니다.</strong>

# Parent창에서 modal에 props를 사용한 값 전달
메인화면에서 import된 modal에 값을 전달을 위해 사용한 내용입니다.

```html
<!-- 
    메인 화면
-->
<b-button @click="showModal('id1')">Show Modal</b-button>
<b-modal
    ref="child-modal"
    title="Child Modal"
    @ok="save">
    <child-modal-template v-bind:pid="id"></child-modal-template>
</b-modal>

<script>
    import CModal from "./ChildModal"
    //... 생략 ...
    data() {
        return {
            id: ''
        }
    },
    components: {
        'child-modal-template': CModal
    },
    methods: {
        showModal(id) {
            this.id = id;
            this.$refs['child-modal'].show();
        }
    }
</script>
```
메인화면에서 버튼을 클릭하면 modal화면이 보여지게 된다.
child-modal-template에 props를 사용하여 값을 전달하는 부분이
> v-bind:pid="id"

이 부분이 된다.
props에 pid란 props이름으로 id값을 전달하는 것이다.

그럼 child modal에서 props를 값을 어떻게 받는지 보자.
```javascript
// 스크립트 부분만 작성함
props: ['pid'],
created() {
    console.log(this.pid);
}
```
위와같이 props로 전달된 값을 받을수 있다.

# 전달하고 싶은 값이 한개 이상일때는?
child modal에 넘겨야 하는 값이 한개이상일경우의 넘길 값을 정의하고 그 값을 받아 사용하는 방법이다.
```javascript
// v-bind:user="user"
// 메인화면
data() {
    return {
        user: {
            id: '',
            name: ''
        }
    }
}

// child
props: ['user'],
created() {
    console.log(user.id);
    console.log(user.name);
}
```
