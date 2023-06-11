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
  <v-text-field v-model="inputtingDescription" />
  <v-btn class="save-button bg-pink-lighten-1" @click="postTodo()">post</v-btn>
</template>
<style></style>
