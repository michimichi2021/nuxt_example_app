<template>
  <v-card class="mx-auto mt-5" max-width="500">
    <v-list v-for="todo in todos" :key="todo.id" width="300" class="d-flex justify-space-between align-center bg-purple-lighten-5">
      <v-list-item>{{ todo.description }}</v-list-item>
      <v-btn @click="deleteTodo(todo.id)" class="delete-button bg-blue-darken-4 mr-2">delete</v-btn>
    </v-list>
  </v-card>
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
</style>
