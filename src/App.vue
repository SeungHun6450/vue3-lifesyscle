<template>
  <h1> {{ count }} </h1>
</template>

<script>
export default{
  data() {
    return {
      count: 2
    }
  },
  // LifeCycle
  beforeCreate() {
    // 컴포넌트가 연결되기 전 상태
    console.log('Before Create!', this.count) // this.count는 undefined
  },
  // created와 mounted 작성 순서와 상관 없이 created가 먼저 이후에 mounted가 생성
  created() { // ★제일 많이 사용
    // App.vue 라는 하나의 컴포넌트를 초기화 하는 과정에서 컴포넌트가 생성된 직후에
    // 해당하는 함수의 내용이 실행될 수 있도록 구조가 제공
    console.log('Created!', this.count)
    console.log(document.querySelector('h1')) // null
  },
  beforeMount() {
    // html과 연결되기 전 상태
    console.log('Before Mount!')
    console.log(document.querySelector('h1')) // null
  },
  mounted() { // ★ 연결 직후 많이 사용
    // 화면에 실제 컴포넌트가 출력이 되고 숫자 데이터가 나오고 나서 mounted가 실행
    console.log('Mounted!')
    console.log(document.querySelector('h1'))
  }
}
</script>