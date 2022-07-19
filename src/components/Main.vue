<template>
  <main>
    <div class="container">
        <div class="row">
            <div class="col-10 m-auto text-center">
                <SongCard />
            </div>
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
    }
}
</script>

<style>

</style>