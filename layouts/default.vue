<template>
  <div class="container">
    <slot name="header"></slot>
    <!-- <slot name="my-slot" v-bind="boundedVar"></slot> -->
    <Nabar/>
    <slot></slot>
  </div>
</template>
<script setup lang="ts">

</script>
<style>
  .container {
    color: red;
  }

  footer {
    background-color: orange;
    color: white;
    text-align: center;
  }

  html {
    font-family: 'Roboto', sans-serif;
  }
</style>
