<script setup>
import { reactive, ref } from 'vue'

//reactive の使い方
const counter = reactive({
  count:0
})

console.log(counter.count)
counter.count++

//refの使い方
const message = ref("Hello World")
//文字を代入する関数か？
console.log(message)
message.value = "Changed"
</script>

<template>
  <h1>{{ message }}</h1>
  <p>Count is: {{ counter.count }}</p>
</template>

<!-- 参考リンク -->
<!-- https://ja.vuejs.org/tutorial/#step-2 -->