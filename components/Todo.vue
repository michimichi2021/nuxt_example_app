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
  <div class="container">
    <h1>Todo</h1>
    <div>
      <TodoPostForm @postTodo="postTodo" />
    </div>
    <div class="tweet-container">
      <p v-if="todos.length <= 0">No todos have been added</p>
      <ul>
        <TodoList :todos="todos" @delete-todo="deleteTodo" />
      </ul>
    </div>
  </div>
</template>

<style>
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .tweet-list {
    list-style: none;
    margin-bottom: 12px;
    border-radius: 4px;
    font-size: 12px;
    display: flex;
    justify-content: space-between;
    background-color: aliceblue;
    padding: 8px 20px;
    width: 300px;
  }

  .payment {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 80px;
    width: 400px;
    background-color: aliceblue;
  }

  label {
    font-size: 20px;
    font-weight: bold;
  }
</style>
