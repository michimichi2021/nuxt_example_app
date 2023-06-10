<template>
  <li v-for="todo in todos" :key="todo.id" class="todo-list">
    <span>{{ todo.description }}</span>
    <button @click="deleteTodo(todo.id)" class="delete-button">delete</button>
  </li>
</template>
<script setup lang="ts">
  import { defineProps } from 'vue'
  type Todo = {
    id: number
    description: string
  }
  type Props = {
    todos: Todo[]
  }

  defineProps<Props>()
  const emit = defineEmits(['delete-todo'])
  const deleteTodo = (id: number) => {
    emit('delete-todo', id)
  }
</script>
<style>
  .todo-list {
    list-style: none;
    margin-bottom: 12px;
    border-radius: 4px;
    font-size: 12px;
    display: flex;
    justify-content: space-between;
    background-color: rgb(204, 219, 233);
    padding: 8px 20px;
    width: 300px;
  }
</style>
