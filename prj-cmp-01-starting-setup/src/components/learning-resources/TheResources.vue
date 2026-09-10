<template>
  <div>
    <base-card>
      <base-button
        @click="setselectedTab('StoredResources')"
        :mode="storedResButtonMode"
      >
        The Resources
      </base-button>

      <base-button
        @click="setselectedTab('AddResource')"
        :mode="addResButtonMode"
      >
        Add Resource
      </base-button>
    </base-card>

    <keep-alive>
      <component :is="selectedTab"></component>
    </keep-alive>
  </div>
</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue';

export default {
  components: {
    StoredResources,
    AddResource,
  },

  computed: {
    storedResButtonMode() {
      return this.selectedTab === 'StoredResources' ? null : 'flat';
    },

    addResButtonMode() {
      return this.selectedTab === 'AddResource' ? null : 'flat';
    },
  },

  data() {
    return {
      selectedTab: 'StoredResources',

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

  provide() {
    return {
      storeResources: this.storeResources,
      addResource: this.addResource,
      removeResource: this.removeResource,
    };
  },

  methods: {
    setselectedTab(tabName) {
      this.selectedTab = tabName;
    },

    addResource(title, description, url) {
      const newResource = {
        id: new Date().toDateString(),
        title: title,
        description: description,
        link: url,
      };

      this.storeResources.unshift(newResource);
      this.selectedTab = 'StoredResources';
    },

    removeResource(resId) {
      const index = this.storeResources.findIndex((res) => res.id === resId);

      if (index !== -1) {
        this.storeResources.splice(index, 1);
      }
    },
  },
};
</script>
