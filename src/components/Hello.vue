<script setup>
defineProps({
  msg: String,
});
const dataTest = "これはデータです";


</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ dataTest }}</h1>
    //v-bind:属性名
    <input v-text="dataTest" v-bind:placeholder='dataTest'></input>
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
