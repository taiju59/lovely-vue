<template>
  <div id="app">
    <VsCol vs-offset="1">
      <br />
      <h1>Lovely Vue</h1>
      <br />
      <VsRow>
        <VsInput v-model="message" size="large" />
        <VsButton :disabled="isDisabled" class="add_button" @click="add">
          追加
        </VsButton>
      </VsRow>
      <br />
      <template v-if="todos.length === 0">
        <VsRow>
          タスクはありません
        </VsRow>
      </template>
      <template v-else>
        <VsRow v-for="todo in todos" :key="todo.id" vs-w="10">
          <TaskCard :id="todo.id" :text="todo.text" @remove-task="remove" />
        </VsRow>
      </template>
    </VsCol>
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

<style>
.add_button {
  margin-left: 8px;
}
</style>
