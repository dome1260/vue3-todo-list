<template>
  <label> Todo : </label>
  <input v-model="todo"  type="text">
  <button @click="addTodo()">
    add
  </button>

  <p v-for="(list, i) in lists" :key="`todo-item-${i + 1}`">
    {{ list }} <button @click="removeTodo(i)"> remove </button>
  </p>
</template>

<script setup>
import { ref } from 'vue'

// ref => string , number , array , boolean
// reactive => object

const todo = ref('')

const lists = ref([])

const addTodo = () => {
  lists.value.push(todo.value)

  todo.value = ''
}

const removeTodo = (index) => {
  lists.value.splice(index, 1)
}

</script>
