<template>
    <form @submit.prevent="handleSubmit">
        <label>
            Name:
            <input v-model="emoji.name" required>
        </label>
        <label>
            Image URL:
            <input v-model="emoji.image" required>
        </label>
        <button>Add</button>
    </form>
</template>

<script>
export default {
  data() {
    return {
      emoji: {}
    };
  },
  props: {
    onAdd: Function
  },
  methods: {
    handleSubmit() {
      this.onAdd(this.emoji)
        .then(() => {
          this.emoji = {};
        });
    }
  }
};
</script>

<style>

</style>
