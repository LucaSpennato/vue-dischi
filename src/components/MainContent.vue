<template>
  <main>
    <div class="container p-5 text-center">
        <div class="row">
            <div class="row col-10 m-auto text-white" 
            v-if="songs.length === 10" >

                <SongCard
                v-for="(song, index) in songs" :key="index"
                :title="song.title"
                :author="song.author"
                :year="song.year"
                :genre="song.genre"
                :posterImg="song.poster"
                />
            </div>

            <div v-else class="col-2 m-auto fs-1 text-light">
                <div class="page-loader">
                    Ciao mi sto caricando
                </div>
            </div>

        </div>

        <!-- <div class=" fs-1 text-dark py-5 my-5">
            <div class="page-loader">
                ciao
            </div>
        </div> -->
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
        height: calc(100vh + 5rem);

        .page-loader{
            animation: 2s ease-out 0s infinite rotate;
            width: 10rem;
        }

        @keyframes rotate{

            100% {
                transform: rotate(360deg);
            }

        }
        
    }

</style>