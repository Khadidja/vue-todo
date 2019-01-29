<template>
  <div>
    <h1>To Do List</h1>
    <div v-bind:key="e.id" v-for="e in todos">
      <TodoItem v-bind:todo="e" v-on:delete-todo="$emit('delete-todo', e.id)"/>
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: ["todos"]
};
</script>

<style scoped>
</style>