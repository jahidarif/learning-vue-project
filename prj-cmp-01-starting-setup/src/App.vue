<template>
  <StoredResource :resources="storeResources"></StoredResource>
</template>
<script>
import StoredResource from './components/learning-resources/StoredResource.vue';
export default {
  components: {
    StoredResource,
  },
  data() {
    return {
      storeResources: [
        {
          id: 'offcicial-guide',
          title: 'Official Guide',
          description:
            'The official Vue.js guide is a comprehensive resource for learning Vue.js, covering everything from the basics to advanced topics.',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description:
            'Google is a search engine that provides a way to find information on the web.',
          link: 'https://google.com',
        },
      ],
    };
  },
};
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');
* {
  box-sizing: border-box;
}
html {
  font-family: 'Roboto', sans-serif;
}
body {
  margin: 0;
}
</style>
