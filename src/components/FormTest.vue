<template>
  <div class="hello">
    <h2>Contact US</h2>
    <form v-on:submit.prevent="submitForm">
      <div class="form-group">
        <label for="name">Name</label>
        <input
          type="text"
          class="form-control"
          id="name"
          placeholder="Your name"
          v-model="formName"
        />
      </div>
      <div class="form-group">
        <button class="btn btn-primary">Submit</button>
      </div>
    </form>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "FormTest",
  setup() {
    const formName = ref("");
    return {
      formName,
    };
  },
};
</script>

<style scoped>
</style>
