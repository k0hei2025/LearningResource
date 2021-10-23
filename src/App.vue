<template>
  <the-header></the-header>

  <cards>
    <template v-slot:default>
      <button v-on:click="resourceSwapHandler('stored-resource')">
        StoredResource
      </button>

      <button v-on:click="resourceSwapHandler('add-resource')">
        Add Resource
      </button>
    </template>

    <template v-slot:cardHeader>
      <keep-alive>
        <component v-bind:is="storedResource" />
      </keep-alive>
    </template>
  </cards>
</template>

<script>
import cardVue from './component/ux/card.vue';
import header from './component/TheHeader.vue';
import storedResource from './component/TheStoredResource.vue';
import addResource from './component/TheAddResource.vue';
import { inject } from '@vue/runtime-core';
export default {
  components: {
    'the-header': header,
    'stored-resource': storedResource,
    'add-resource': addResource,
    cards: cardVue
  },
  data() {
    return {
      storedResource: 'stored-resource',
      dataContainer: [
        {
          id: new Date().toISOString(),
          title: 'Google',
          description: 'Its a website where you search anything',
          link: 'http://www.google.com'
        }
      ]
    };
  },

  provide() {
    return {
      resources: this.dataContainer,
      addResource: this.addResource,
      deleteResource: this.deleteHandler
    };
  },
  methods: {
    resourceSwapHandler(compName) {
      this.storedResource = compName;
      console.log('fsdfsd', inject);
    },
    addResource(title, description, link) {
      this.dataContainer.push({
        id: new Date().toISOString(),
        title: title,
        description: description,
        link: link
      });
      console.log(this.dataContainer);
    },
    deleteHandler(id) {
      console.log('delete Handl');
      this.dataContainer.splice(id, 1);
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
