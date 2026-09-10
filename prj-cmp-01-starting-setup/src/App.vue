<template>
  <ul></ul>
</template>
<script>
export default {
  data() {
    return {
      storeResources: [
        {
          id: 'offcicial-guide',
          tite: 'Official Guide',
          description:
            'The official Vue.js guide is a comprehensive resource for learning Vue.js, covering everything from the basics to advanced topics.',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          tite: 'Google',
          description:
            'Google is a search engine that provides a way to find information on the web.',
          link: 'https://google.com',
        },
      ],
    };
  },
};
</script>
