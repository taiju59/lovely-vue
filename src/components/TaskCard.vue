<template>
  <VsCard>
    <h3>{{ text }}</h3>
    <div slot="footer">
      <VsRow vs-justify="flex-end">
        <VsButton icon="delete" color="gray" @click="remove"></VsButton>
      </VsRow>
    </div>
  </VsCard>
</template>

<script>
export default {
  name: "TaskCard",
  props: {
    id: {
      type: Number,
      required: true
    },
    text: {
      type: String,
      default: ""
    }
  },
  methods: {
    remove() {
      console.log(`remove: ${this.id}`);
      this.$emit("remove-task", this.id);
    }
  }
};
</script>

<style></style>
