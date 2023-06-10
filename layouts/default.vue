<template>
  <header>
    <h1>Todo</h1>
    <nav class="gnav">
      <ul class="menu">
        <li><NuxtLink to="https://nuxtjs.org">Nuxtのウェブサイト</NuxtLink></li>
        <li><NuxtLink to="https://twitter.com">お問い合わせ</NuxtLink></li>
      </ul>
    </nav>
  </header>
  <div class="container">
    <slot></slot>
  </div>
</template>
<script setup lang="ts"></script>
<style>
  html {
    font-family: 'Roboto', sans-serif;
  }
  header {
    width: 100%;
    height: 50px;
    background: pink;
    padding: 20px 50px;
    box-sizing: border-box;
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    align-items: center;
  }
  header .gnav .menu {
    display: flex;
  }

  header .gnav .menu li {
    list-style: none;
  }

  header .gnav .menu li + li {
    margin-left: 40px;
  }

  .container {
    margin-top: 50px;
  }
</style>
