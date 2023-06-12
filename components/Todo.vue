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
  const titleState = useTitle()
  const { title }= titleState
</script>
<template>
  <div class="flex flex-md-column mx-auto mt-5">
    <div class="d-flex  flex-column mb-5">
      <v-list class="text-h4 mx-auto">{{ title }}</v-list><br/>
      <v-btn @click="titleState.changeTitle('タスク管理アプリ')">changeTitle</v-btn>
    </div>
    <TodoPostForm @postTodo="postTodo" />
    <v-list v-if="todos.length <= 0">No todos have been added</v-list>
    <ul>
      <TodoList :todos="todos" @delete-todo="deleteTodo" />
    </ul>
  </div>
</template>
