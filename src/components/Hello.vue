<script setup>
import { ref } from "vue";

defineProps({
  msg: String,
});

//　バインディング

// テキストバインディング v-text
// 属性バインディング v-bind:属性名 v-bind:href='/src/sample.png'
// イベントバインディング v-on:イベント v-on:click='handleClick' @click='handleClick'
// 双方向バインディング const value = ref('') v-model="value"

const dataTest = "これはデータです";

const myMethod = () => {
  alert("myMethod");
};
const inputValue = ref("");

// ディレクティブ

// v-for
//配列
const fruitsArray = ["apple", "banana", "orange"];
//オブジェクト
const fruitsObjct = [
  { id: 0, name: "apple" },
  { id: 1, name: "banana" },
  { id: 2, name: "orange" },
];

// v-if = '条件' v-else
// v-show = '条件'
const number = 4;
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ dataTest }}</h1>
    <input v-bind:placeholder="dataTest" v-model="inputValue" />
    <button @click="myMethod">myMethod</button>
    <div>{{ inputValue }}</div>
    <br />
    <hr />
    <br />
    <p>配列ループ</p>
    <ul>
      <li v-for="fruit in fruitsArray" v-bind:key="fruit">
        {{ fruit }}
      </li>
    </ul>

    <p>オブジェクトループ</p>
    <ul>
      <li v-for="fruit in fruitsObjct" v-bind:key="fruit.id">
        {{ fruit.name }}
      </li>
    </ul>
    <p v-if="number < 3">数字は3より小さい</p>
    <p v-else>数字は3より大きい</p>
    <p v-show="number === 4">数字は4</p>
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
