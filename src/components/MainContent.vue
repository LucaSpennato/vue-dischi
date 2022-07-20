<template>
  <main>
    <div class="container p-5 text-center">
        <div class="row">
            <div class="row col-10 m-auto text-white" 
            v-if="isPageLoaded" >

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
                    <i class="bi bi-hourglass"></i>
                </div>
            </div>

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
            isPageLoaded: false,
        }
    },
    methods: {

        getAlbums: function(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response)=>{
                this.songs = response.data.response ;
                console.log(this.songs);
                
                setTimeout(() => {
                    this.isPageLoaded = true;
                }, 2000);
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
    @import '~bootstrap-icons/font/bootstrap-icons.css';

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