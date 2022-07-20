<template>
  <main>
    <div class="container p-5 text-center">
        <div class="row">
            <div class="row col-10 m-auto text-white" 
            v-if="isPageLoaded">

                <!-- <div class="col-12">
                    <select class="form-select" v-model="selectedValue" @click="filteredSearch(selectedValue)">
                        <option value="">Nessuna selezione</option>
                        <option>Jazz</option>
                        <option>Rock</option>
                        <option>Pop</option>
                        <option>Metal</option>
                    </select>
                </div> -->

                <SongCard
                v-for="(song, index) in filteredSongs" :key="index"
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
            filteredSongs: [],
            // selectedValue: '',
        }
    },
    methods: {

        filteredSearch: function(needle){
          return this.filteredSongs = [...this.songs].filter((element) => element.genre.toLowerCase().includes(needle.toLowerCase()));
        },

        getAlbums: function(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response)=>{
                this.songs = response.data.response ;

                setTimeout(() => {
                    this.isPageLoaded = true;
                }, 2000);
                
                // perchè richiamarla qua? Perchè il tutto avviene in modo asincrono, quindi non troveremmo
                // nulla senza richiamarla qua. Quel che succede è che qua fa la chiamata E POI...succede il resto!
                // di fatti mettendo il console in funzione vedremo due log, uno vuoto all'avvio della pagina,
                // ed uno popolato quando la chiamata get sarà completa!
                this.filteredSearch('');
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