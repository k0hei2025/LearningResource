<template>
  <ul>
    <div v-for="i in resources" v-bind:key="i.id">
      <h1>{{ i.title }}</h1>
      <b> {{ i.description }} </b><br />

      <a v-bind:href="i.link"><p>View Resource</p></a>
      <button v-on:click="deleteHandler(i.id)">Delete</button>
    </div>
  </ul>
</template>

<script>
export default {
  inject: ['resources', 'deleteResource'],
  methods: {
    deleteHandler(id) {
      this.deleteResource(id);
    }
  }
};
</script>

<style scoped>
body {
  text-align: center;
}
button {
  position: absolute;
  left: 65%;
  bottom: 55%;
}
p {
  color: #e26a2c;
}
</style>
