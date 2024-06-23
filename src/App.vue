<script setup>
import { ref } from "vue";

import Hello from "./components/Hello.vue";

const childData = ref("");
const updateMessage = (data) => {
  console.log(data);
  childData.value = data;
  console.log(childData);
};
</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125" />

    <div class="wrapper">
      <Hello @sendMessage="updateMessage" msg="You did it!" />
      <p>メッセージ</p>
      <p>{{ childData }}</p>
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
