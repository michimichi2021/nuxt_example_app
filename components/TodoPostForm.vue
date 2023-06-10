<script setup lang="ts">
  import { ref, defineEmits } from 'vue'
  const inputtingDescription = ref<string>('')

  const emit = defineEmits(['postTodo'])
  const postTodo = () => {
    emit('postTodo', inputtingDescription.value)
    inputtingDescription.value = ''
  }
</script>
<template>
  <div class="form-container">
    <input v-model="inputtingDescription" />
    <button class="save-button" @click="postTodo()">post</button>
  </div>
</template>
<style></style>
