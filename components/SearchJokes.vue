<template>
  <form @submit.prevent="onSubmit">
    <label for="search">Search</label>
    <input placeholder="other side dad joke" type="text" v-model="text" />
  </form>
</template>

<script>
export default {
  name: "SearchJokes",
  data() {
    return {
      text: ""
    };
  },
  methods: {
    onSubmit() {
      this.$emit("search-text", this.text);
      this.text = "";
    }
  }
};
</script>

<style></style>
