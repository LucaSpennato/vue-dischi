<template>
  <main class="bg-dark">
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
    }
}
</script>

<style lang="scss">

</style>