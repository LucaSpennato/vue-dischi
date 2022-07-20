<template>
  <div id="app">
      <HeaderComponent @choosedGenre="selection"/>
      <MainContent
      :selectedOption="selectedOption"
      />
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
  data: function(){
    return{
    selectedOption: '',
    }
  },
  methods: {
    selection: function(needle){
      this.selectedOption = needle;
      console.warn(this.selectedOption);
    }

  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';

</style>
