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

하나의 태그에 v-for v-if 같이 사용하지 말것!!! 같이 사용하면 v-if가 우선순위를 갖게 된다.
같이 사용해야 하는경우에는
<template>태그를 만들어서 v-for나 v-if 사용하고 그 하위 태그로 나머지 태그를 사용해서
활용할 수 있다!!!!

v-for에서 배열데이터는 (item, index(옵션)) in items 두개의 인수를 가질 수 있음
v-for를 객체데이터를 반복하면 value값이 반복됨!!!
v-for를 객체데이터를 반복하면 (value,name(옵션), index(옵션)) in myObject 하면 name에는 키가 반복된다. 단, 순서는 보장되지 않는다.
v-for를 사용하면 반드시 key 속성과 함께 사용해야한다!!!

배열 변경 감지
반응형 데이터가 배열 데이터고 변이 메소드를 사용하면 화면을 갱신해 준다.
원본 배열 변경하는 메소드
push()
pop()
shift()
unShift()
복사해서 반환하는 배열
filter(), concat(), slice()
이걸 다시 원본 배열에 다시 할당하더라도, vue는 이것을 잘 최적화하여 바뀌는 부분만 렌더링 한다.
(전체를 다시 렌더링하는 것이 아님)

filter(number => number % 2 === 0)
data() {
return {
numbers: [1,2,3,4,5]
}
},
computed: {
evenNumbers() {
return this.numbers.filter(number => number % 2 === 0)
}
}
이러면 this.numbers는 반응형 데이터고 해당 데이터가 변경되면 계산된 데이터인 computed에
들어있는 데이터도 같이 변경됨

범위가 있는 v-for
v-for도 정수를 사용할 수 있다.
<span v-for = "n in 10"> 주의할 점은 제로베이스가 아니라 1부터 시작함!!!!
