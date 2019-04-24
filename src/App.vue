<template>
  <div id="app">
    <h1>Lovely Vue</h1>
    <input v-model="message" />
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
  })
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
