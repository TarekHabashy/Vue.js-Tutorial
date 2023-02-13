<!-- 参考リンク -->
<!-- https://ja.vuejs.org/tutorial/#step-8 -->

<script setup>
import { ref, computed} from 'vue'


let id = 0

const newTodo = ref('')
const hideCompleted = ref(false)

//TodoListのデータ
const todos = ref([
  { id: id++, text: 'Learn HTML', done: true},
  { id: id++, text: 'Learn Javascript', done: true},
  { id: id++, text: 'Learn Vue', done: false}
])

//TodoListのDoneを切り替える
const filteredTodos = computed(() => { //computed()ってなんやねん
  return hideCompleted.value
    ? todos.value.filter((t)=>!t.done)
    : todos.value
})

//TodoListにTodoを追加
const addTodo=()=>{
  todos.value.push({id: id++, text: newTodo.value, done:false})
  newTodo.value='' //値の初期化
}

//TodoListのTodoを削除
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
    <li v-for="todo in filteredTodos" :key="todo.id">
      <input type="checkbox" v-model="todo.done">
      <span :class="{done : todo.done}">{{ todo.text }}</span>
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>

  <button @click="hideCompleted = !hideCompleted">
    {{ hideCompleted ? 'Show all' : 'Hide completed' }}
  </button>
</template>

<style>
  .done{
    text-decoration: line-through;
  }
</style>


