<template>
  <header></header>

  <button v-on:click="resourceSwapHandler('stored-resource')">
    StoredResource
  </button>

  <button v-on:click="resourceSwapHandler('add-resource')">Add Resource</button>

  <component v-bind:is="storedResource" />
</template>

<script>
import header from './component/TheHeader.vue';
import storedResource from './component/TheStoredResource.vue';
import addResource from './component/TheAddResource.vue';
export default {
  components: {
    header: header,
    'stored-resource': storedResource,
    'add-resource': addResource
  },
  data() {
    return {
      storedResource: 'stored-resource'
    };
  },
  methods: {
    resourceSwapHandler(compName) {
      this.storedResource = compName;
    }
  }
};
</script>

<style scoped></style>
