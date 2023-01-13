<script>
  import HeaderApp from './components/HeaderApp.vue';
  import MainApp from './components/MainApp.vue';

  export default {
    components: {
      HeaderApp,
      MainApp
    }
  }
</script>

<template>

  <HeaderApp/>

  <MainApp/>

</template>

<style lang="scss">
  @use "../node_modules/bootstrap/scss/bootstrap.scss" as *;
  @use "./styles/partials/variables.scss" as *;
  @use "./styles/general.scss" as *;

</style>
