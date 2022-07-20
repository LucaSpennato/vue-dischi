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
  },
  // methods: {
  //   selection: function(needle){
  //     // this.selectedOption = needle;
  //     console.warn();
  //   }

  // }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';

</style>
