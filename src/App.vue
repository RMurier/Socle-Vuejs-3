<template>
<v-app>
  <v-main>
    <router-view />
  </v-main>
</v-app>
</template>

<script>
export default {
  name: 'App',
  watch: {
    $route: {
      immediate: true,
        handler(to, from) {
            document.title = to.meta.title || 'Romain MURIER';
        }
      },
  },
  data: () => ({
  }),
}
</script>
