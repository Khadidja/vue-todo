<template>
  <div class="todo-item">
    <input type="checkbox" checked v-if="todo.completed" v-on:change="markCompleted">
    <input type="checkbox" v-else v-on:change="markCompleted">
    <p v-bind:class="{'completed':todo.completed}">{{todo.title}}</p>
    <button @click="$emit('delete-todo', todo.id)" class="btn-delete">X</button>
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
  border-bottom: solid 1px #d3d3d3;
  display: flex;
  flex-direction: row;
  align-items: center;
  align-content: center;
  justify-content: space-between;
}
.todo-item:hover {
  background: #bfd5e2;
}

.completed {
  text-decoration: line-through;
  text-decoration-color: #474953;
}

.btn-delete {
  background: #baa7b0;
  color: black;
  padding: 0.3rem;
  margin: 1rem;
  font-weight: bold;
}

.btn-delete:hover {
  background: red;
  color: black;
}

input[type="checkbox"] {
  margin: 1rem;
}
</style>
