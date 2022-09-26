<template>
  <h1 @click="increase">
    {{ count }}
  </h1>
  <h1 @click="changeMessage">
    {{ message }}
  </h1>
</template>

<script>
import { ref, computed } from 'vue';

export default {
  setup() {
    const count = ref(0)
    // 현재 count 데이터가 재할당 되는 경우가 없기 때문에 let 이 아닌 const 로 써주자
    const doubleCount = computed(() => {
      return count.value * 2
    })
    function increase() {
      count.value += 1
    }

    const message = ref('Hello world!')
    const reversedMessage = computed(() => {
      return message.value.split('').reverse().join('')
    })
    function changeMessage() {
      message.value = 'Good!?'
    }

    return {
      count,
      increase,
      doubleCount,

      message,
      changeMessage,
      reversedMessage,
    }
  }
}
</script>