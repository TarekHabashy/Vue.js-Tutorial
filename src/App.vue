<!-- 参考リンク -->
<!-- https://ja.vuejs.org/tutorial/#step-5 -->

<script setup>
import { ref } from 'vue'

const text = ref('')
</script>

<template>
  <!-- v-model は onInput(e)みたいな感じ -->
  <input v-model="text" placeholder="Type Here">
  <p>{{ text }}</p>
</template>


