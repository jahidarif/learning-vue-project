<template>
  <ul>
    <LearningResource
      v-for="resource in storeResources"
      :key="resource.id"
      :title="resource.title"
      :description="resource.description"
      :link="resource.link"
    ></LearningResource>
  </ul>
</template>
<script>
import LearningResource from './components/learning-resources/LearningResource.vue';
export default {
  components: {
    LearningResource,
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
