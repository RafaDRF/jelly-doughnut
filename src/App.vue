<template lang="pug">
v-app
  v-main
    home-page
</template>

<script>
import HomePage from './components/HomePage.vue';

export default {
  name: 'App',
  components: {
    HomePage,
  },

  data: () => ({
    //
  }),
};
</script>
