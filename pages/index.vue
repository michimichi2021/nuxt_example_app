<template>
  <div>
    <NuxtLayout name="default">
      <template #header>ヘッダー</template>
      <!-- <template #my-slot="boundedVar"> -->
      <h1>Main Page</h1>
      <Payment/>
    </NuxtLayout>
  </div>
</template>
<script setup lang="ts">
  definePageMeta({
    layout: false,
  });
</script>