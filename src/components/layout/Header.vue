<template>
  <header class="header">
    <h1>To-Do List</h1>
    <div id="nav">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style scoped>
.header {
  background: #b1b5c8;
  text-align: center;
  padding: 16px;
}

.header a {
  color: black;
  padding: 6px;
  text-decoration: none;
}

.header a:hover {
  color: #c7ebf0;
}
</style>
