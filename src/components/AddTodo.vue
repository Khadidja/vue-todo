<template>
  <div class="form-bg">
    <form @submit="addTodo">
      <input v-model="title" type="text" name="title" placeholder="Add To-Do">
      <input type="submit" value="Add">
    </form>
  </div>
</template>

<script>
import uuid from "uuid";

export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        id: uuid.v4(),
        title: this.title,
        completed: false
      };
      this.$emit("add-todo", newTodo);
      this.title = "";
    }
  }
};
</script>

<style scoped>
.form-bg {
  margin: 1rem;
  background: #bfd5e2;
  padding: 1.5rem;
  margin: 0;
}

form {
  display: flex;
}

input[type="text"] {
  flex: 10;
  padding: 6px;
}

input[type="submit"] {
  flex: 2;
  background: #b2abbf;
  margin-left: 6px;
}
</style>
