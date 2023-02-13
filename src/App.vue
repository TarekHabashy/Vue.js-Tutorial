<script setup>
import { ref } from 'vue'

const titleClass = ref("title")

</script>

<template>
  <h1 :class="titleClass">Make me red</h1>
</template>

<style>
.title{
  color: red;
}
</style>

<!-- 参考リンク -->
<!-- https://ja.vuejs.org/tutorial/#step-3 -->