<template>
  <div id="app">
      <HeaderComponent @choosedGenre="selectedOption"/>
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
  methods: {

    selectedOption: function(needle){
      console.warn(needle)
    }

  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';

</style>
