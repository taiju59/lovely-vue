<template>
  <div id="app">
    <h1>Lovely Vue</h1>
    <input v-model="message" />
    <button :disabled="isDisabled" @click="add">追加</button>
    <br />
    <ul>
      <TaskCard
        v-for="todo in todos"
        :id="todo.id"
        :key="todo.id"
        :text="todo.text"
        @remove-task="remove"
      />
    </ul>
  </div>
</template>

<script>
import TaskCard from "@/components/TaskCard.vue";

export default {
  name: "App",
  components: {
    TaskCard
  },
  data: () => ({
    todos: [{ id: 1, text: "ときめき" }],
    message: "Spark joy!"
  }),
  computed: {
    isDisabled() {
      return this.message.length === 0;
    }
  },
  methods: {
    add() {
      const newTodo = {
        id: this.todos.length + 1,
        text: this.message
      };
      this.todos.push(newTodo);
      this.message = "";
    },
    remove(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
};
</script>

<style></style>
