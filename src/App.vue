<template>
  <div id="app">
    <h1>Lovely Vue</h1>
    <input v-model="message" />
    <button @click="add">追加</button>
    <br />
    <ul>
      <li v-for="todo in todos" :key="todo.id" class="task-card">
        {{ todo.text }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    todos: [{ id: 1, text: "ときめき" }],
    message: "Spark joy!"
  }),
  methods: {
    add() {
      const newTodo = {
        id: this.todos.length + 1,
        text: this.message
      };
      this.todos.push(newTodo);
      this.message = "";
    }
  }
};
</script>

<style>
.task-card {
  border: solid 1px;
  margin: 5px;
  padding: 2px;
  width: 250px;
}
</style>
