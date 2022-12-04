프라임워크 : Vue 일정한 구조를 제공하여 정해진 규칙대로 사용하는 것!!
라이브러리: React 가져다 사용만 하면 됨 like console.log() 처럼

mount: 연결

const vm = Vue.createApp(App).mount('#app') // vm은 인스턴스를 반환 받음 -> 그리고 이러한 인스턴에 사용가능한 메서드,속성들이 있음

$props
$el
$options
$parent
$root
$slots
$refs
$attrs
$watch()
$emit()
$forceUpdate()
$nextTick()

라이프사이클훅

1. beforeCreate ->> 실행될 것들
2. created ->> 실행될 것들
   template option 유무에 따라 동작이 달라짐
3. beforeMount ->> 연결 직전 상태
4. mounted
   https://v3-docs.vuejs-korea.org/guide/essentials/lifecycle.html

템플릿 문법

보간법
Mustache(이중 중괄호) <span>{{ msg }}</span>
v-once디렉티브 <span v-once>{{ msg }}</span> 1번만 렌더링되고 반응성이 사라짐
원시 HTML
