<template>
  <div id="app">
      <HeaderComponent/>
      <MainContent/>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainContent from './components/MainContent.vue';

export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainContent,
  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';

</style>
