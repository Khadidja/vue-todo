<template>
  <div class="todo-item" v-bind:class="{'completed':todo.completed}">
    <p>
      <input type="checkbox" checked v-if="todo.completed" v-on:change="markCompleted">
      <input type="checkbox" v-else v-on:change="markCompleted">
      {{todo.title}}
      <button @click="$emit('delete-todo', todo.id)" class="btn-delete">X</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markCompleted() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.todo-item {
  border-bottom: solid 1px;
}
.todo-item:hover {
  background: #d3d3d3;
}
.completed {
  text-decoration: line-through;
}

.btn-delete {
  background: red;
  color: white;
  padding: 0.2rem;
  font-weight: bold;
}
</style>
