<template>
  <the-header></the-header>

  <card>
    <button v-on:click="resourceSwapHandler('stored-resource')">
      StoredResource
    </button>

    <button v-on:click="resourceSwapHandler('add-resource')">
      Add Resource
    </button>
  </card>

  <div>
    <keep-alive>
      <component v-bind:is="storedResource" />
    </keep-alive>
  </div>
</template>

<script>
import cardVue from './component/ux/card.vue';
import header from './component/TheHeader.vue';
import storedResource from './component/TheStoredResource.vue';
import addResource from './component/TheAddResource.vue';
export default {
  components: {
    'the-header': header,
    'stored-resource': storedResource,
    'add-resource': addResource,
    card: cardVue
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

<style>
html {
  font-family: sans-serif;
}
body {
  margin: 0;
}
</style>
