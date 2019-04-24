<template>
  <div id="app">
    <h1>Lovely Vue</h1>
    <input @input="onInput" />
    <br />
    {{ message }}
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    message: "Spark joy!"
  }),
  methods: {
    onInput(event) {
      const text = event.target.value;
      this.message = text;
    }
  }
};
</script>

<style></style>
