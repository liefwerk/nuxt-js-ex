<template>
  <div class="">
    <nuxt-link to="/jokes">Back to the Jokes</nuxt-link>
    <h2>
      {{ this.joke.joke }}
    </h2>
    <hr />
    <small>Joke ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      joke: {}
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      );
      this.joke = res.data;
    } catch (error) {
      console.log(error);
    }
  }
};
</script>

<style></style>
