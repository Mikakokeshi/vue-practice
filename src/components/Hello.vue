<script setup>
import { ref } from "vue";

defineProps({
  msg: String,
});
const dataTest = "これはデータです";

const myMethod = () => {
  alert("myMethod");
};
const inputValue = ref("");
</script>

// テキストバインディング v-text // 属性バインディング v-bind:属性名
v-bind:href='/src/sample.png' // イベントバインディング v-on:イベント
v-on:click='handleClick' @click='handleClick' // 双方向バインディング const
value = ref('') v-model="value"

<template>
  <div class="greetings">
    <h1 class="green">{{ dataTest }}</h1>
    <input v-bind:placeholder="dataTest" v-model="inputValue" />
    <button @click="myMethod">myMethod</button>
    <div>{{ inputValue }}</div>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}
</style>
