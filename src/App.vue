<!-- 参考リンク -->
<!-- https://ja.vuejs.org/tutorial/#step-6 -->

<script setup>
import { ref } from 'vue'

let id = 0

const newTodo = ref('')

//id++することでn+1できて便利
const todos = ref([
  { id: id++, text: 'Learn HTML'},
  { id: id++, text: 'Learn Javascript'},
  { id: id++, text: 'Learn Vue'}
])

const addTodo=()=>{
  todos.value.push({id: id++, text: newTodo.value})
  newTodo.value='' //値の初期化
}

const removeTodo=(todo)=>{
  todos.value = todos.value.filter((t) => t !== todo) //t とは → filterの返り値
}
</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo"> <!-- v-model は onInputのこと-->
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
</template>


