<template>
  <div>
    <NuxtLayout name="default">
      <Todo />
    </NuxtLayout>
  </div>
</template>
<script setup lang="ts">
  import Todo from '~/components/Todo.vue'
  definePageMeta({
    layout: false
  })
</script>
