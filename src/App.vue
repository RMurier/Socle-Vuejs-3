<template>
<v-app>
  <v-main>
    <AppBar />
    <router-view />
  </v-main>
</v-app>
</template>
<style>
.v-main {
  display: flex;
  flex-direction: column;
}
</style>
<script>
import AppBar from './shared/appbar.vue';
export default {
  name: 'App',
  watch: {
    $route: {
      immediate: true,
        handler(to, from) {
            document.title = to.meta.title || 'Socle Vue.JS 3';
        }
      },
  },
  data: () => ({}),
  components: {
    AppBar
  }
}
</script>
