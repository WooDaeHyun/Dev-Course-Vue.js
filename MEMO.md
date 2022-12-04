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
