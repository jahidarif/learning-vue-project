<template>
  <ul>
    <LearningResource
      v-for="resource in storeResources"
      :key="resource.id"
      :id="resource.id"
      :title="resource.title"
      :description="resource.description"
      :link="resource.link"
    ></LearningResource>
  </ul>
</template>

<script>
import LearningResource from './LearningResource.vue';

export default {
  inject: ['storeResources'],

  components: {
    LearningResource,
  },
};
</script>