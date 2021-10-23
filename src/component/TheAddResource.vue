<template>
  <h1>The Add Resource</h1>
  <form v-on:submit.prevent="submitHandler">
    <b>Title</b> <br />
    <input type="text" placeholder="Enter Title" ref="titleRef" />
    <b>Description</b> <br />
    <textarea cols="80" placeholder="Enter Description" v-model="description" />
    <br />
    <b>Link</b> <br />
    <input type="text" placeholder="EnterLink" ref="linkRef" />

    <button class="buttonC">Add Resource</button>
  </form>
</template>

<script>
export default {
  inject: ['addResource'],
  data() {
    return {
      description: ''
    };
  },

  methods: {
    submitHandler() {
      this.addResource(
        this.$refs.titleRef.value,
        this.description,
        this.$refs.linkRef.value
      );
    }
  }
};
</script>

<style scoped>
input {
  padding-right: 50vh;
  border-style: groove;
  border-block-color: white;
}
body {
  font-family: roboto, sans-serif;
}
.buttonC {
  margin-top: 1rem;
}
</style>
