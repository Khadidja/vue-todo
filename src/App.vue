<template>
  <div id="app">
    <Header/>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo"/>
  </div>
</template>

<script>
import Header from "./components/layout/Header";
import AddTodo from "./components/AddTodo";
import Todos from "./components/Todos";

export default {
  name: "app",
  components: {
    Header,
    AddTodo,
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Get coffee",
          completed: true
        },
        {
          id: 2,
          title: "Create a REST API with Restify",
          completed: true
        },
        {
          id: 3,
          title: "Start learning Vue Js",
          completed: false
        }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(e => e.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
    "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
}
</style>
