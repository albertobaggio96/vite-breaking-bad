<script>
  import HeaderApp from './HeaderApp.vue';
  import MainApp from './MainApp.vue';

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
