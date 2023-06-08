<template>
  <div class="container">
    <h1>最近の支出</h1>
    <input v-model="item1.name" />
    <input v-model="item1.price" />
    <button v-on:click="clear">Clear</button>
    <div class="payment">
      <label>{{ item1.name }}</label>
      <label>{{ priceLabel }}</label>
      <a v-bind:href="url1">リンク</a>
      <button v-on:click="buy(item1.name)">BUY</button>
    </div>
  </div>
</template>

<script setup lang="ts">
  import { reactive, watch, toRefs } from 'vue'

  const item1 = reactive({
    name: 'カレー',
    price: 40000
  })
  const url1 = 'https://www.wantedly.com/companies/tabian/post_articles/330003'
  const buy = (itemName: string) => {
    alert('Are you sure to buy' + itemName + '?')
  }
  const clear = () => {
    item1.name = ''
    item1.price = 0
  }

  const priceLabel = ref<string>(item1.price + ' yen')
  const budge = 50000
  const { price } = toRefs(item1)
  watch(price, () => {
    if (price.value > budge * 2) {
      priceLabel.value = 'toooooo expensive..'
    } else if (price.value > budge) {
      priceLabel.value = 'expensive..'
    } else {
      priceLabel.value = price.value + ' yen'
    }
  })
</script>

<style>
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
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
