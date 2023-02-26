<template>
  <main class="container">
    <br />
    <h3>Chuck Norris Joke Generator</h3>

    <blockquote v-if="joke">
      {{ joke.value }}
      <footer>
        <cite>Joke ID: {{ joke.id }}</cite>
      </footer>
    </blockquote>

    <button :aria-busy="isLoading" @click="getRandomJoke">
      {{ isLoading ? "" : "Get another joke" }}
    </button>
  </main>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  data() {
    return {
      joke: null,
      isLoading: true,
    };
  },
  methods: {
    async getRandomJoke() {
      this.isLoading = true;
      const response = await fetch("https://api.chucknorris.io/jokes/random");
      response.json().then((r) => {
        this.joke = r;
        this.isLoading = false;
      });
    },
  },
  created() {
    this.getRandomJoke();
  },
});
</script>
