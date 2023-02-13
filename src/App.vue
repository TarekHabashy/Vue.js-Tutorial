<!-- 参考リンク -->
<!-- https://ja.vuejs.org/tutorial/#step-6 -->

<script setup>
import { ref } from 'vue'

const awesome = ref(true)

//真偽値の反転
const toggle = () => {
  awesome.value = !awesome.value
}
</script>

<template>
  <button @click="toggle">toggle</button>
  <!-- v-if v-elseで分岐する -->
  <h1 v-if="awesome">Vue is awesome!</h1>
  <h1 v-else>Oh no😭</h1>
</template>


