<template>
  <li class="task-card">
    {{ text }}
  </li>
</template>

<script>
export default {
  name: "TaskCard",
  props: {
    text: {
      type: String,
      default: ""
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
