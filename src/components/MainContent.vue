<template>
  <main>
    <div class="container p-5">
        <div class="row col-10 m-auto text-center">
            <SongCard />
        </div>
    </div>
  </main>
</template>

<script>
import SongCard from './SongCard.vue';

export default {
    name: 'MainComponent',
    components:{
        SongCard,
    },
    data: function(){
        return{

        }
    },
    methods: {

        showStuff: function(){
            console.log('ciao');
        }

    },
    created(){
        this.showStuff();
    }
}
</script>

<style lang="scss">
    @import '../style/variables.scss';

    main{
        background-color: $mainBgColor;
        height: 92vh;
    }

</style>