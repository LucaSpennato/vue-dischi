<template>
  <main>
    <div class="container p-5">
        <div class="row col-10 m-auto text-center text-white">
            <SongCard v-for="(song, index) in songs" :key="index"
            :title="song.title"
            :author="song.author"
            :year="song.year"
            :genre="song.genre"
            :posterImg="song.poster"
            />
        </div>
    </div>
  </main>
</template>

<script>
import SongCard from './SongCard.vue';
import axios from 'axios';

export default {
    name: 'MainComponent',
    components:{
        SongCard,
    },
    data: function(){
        return{
            songs: [],
        }
    },
    methods: {

        getAlbums: function(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response)=>{
                // console.log(response.data.response);
                this.songs = response.data.response ;
                console.log(this.songs)
            })
            .catch((error)=>{
                console.log(error);
            })
            
        }

    },
    created(){
        this.getAlbums();
    }
}
</script>

<style lang="scss">
    @import '../style/variables.scss';

    main{
        background-color: $mainBgColor;
    }

</style>