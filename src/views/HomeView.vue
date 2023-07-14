<script lang="ts">
export default {
  data() {
    return {
      clicks: 0,
      isRed: true,
      show: true,
      list: [1, 2, 3],
      checkedNames: { name: "Jack" },
    };
  },
};
</script>

<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" /> -->
  </div>
  <h1>{{ clicks }}</h1>
  <button type="button" @click="clicks += 1">Click it!</button>
  <button @click="show = !show">Toggle List</button>
  <button @click="list.push(list.length + 1)">Push Number</button>
  <button @click="list.pop()">Pop Number</button>
  <button @click="list.reverse()">Reverse List</button>

  <ul v-if="show && list.length">
    <li v-for="item of list" :key="item">{{ item }}</li>
  </ul>
  <p v-else-if="list.length">List is not empty, but hidden.</p>
  <p v-else>List is empty.</p>
</template>

<style>
.red {
  color: red;
}
</style>
