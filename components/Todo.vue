<script setup lang="ts">
  import { ref } from 'vue'
  import TodoPostForm from './TodoPostForm.vue'
  import TodoList from './TodoList.vue'

  const todos = ref([{ id: 1, description: '起床' }])

  const postTodo = (description: string) => {
    const todo = { id: Math.random(), description }
    todos.value.push(todo)
  }
  const deleteTodo = (id: number) => {
    todos.value = todos.value.filter((t) => t.id !== id)
  }
</script>
<template>
  <div class="flex flex-md-column mx-auto mt-5">
    <TodoPostForm @postTodo="postTodo" />
    <v-list v-if="todos.length <= 0">No todos have been added</v-list>
    <ul>
      <TodoList :todos="todos" @delete-todo="deleteTodo" />
    </ul>
  </div>
</template>
