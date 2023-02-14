<script setup lang="ts">
import MyPractice from './components/MyPractice.vue';
</script>

<template>
  <h1>Typescript</h1>
  <MyPractice
      initialMessage="ボタンを押してください。"
      clickedMessage="ボタンが押されました！"
      buttonLabel="ボタン"
    />
  <MyPractice
    initialMessage="スイッチを押して！"
    clickedMessage="スイッチが押された！"
    buttonLabel="スイッチ"
  />
</template>
<style scoped>
</style>
