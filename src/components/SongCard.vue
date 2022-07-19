<template>

  <div class="card ms_card col-2 m-2 p-2">
    <div class="card-body p-0">
        <img class="img-fluid" 
          :src="posterImg"
          :alt="`Poster image of ${title}`">
        <h5 class="card-title text-light my-3">{{ title }}</h5>
        <h5 class="card-subtitle text-muted fs-6 mb-1">{{ author }}</h5>
        <h6 class="card-subtitle mb-2 text-muted fs-6">{{ year }}</h6>
    </div>
  </div>

</template>

<script>
export default {
  name: "SongCard",
  props:{
    title: String,
    author: String,
    year: String,
    genre: String,
    posterImg: String,
  }
};
</script>

<style lang="scss">
    @import '../style/variables.scss';

    div.ms_card{
        background-color: $cardbgColor;
        height: 20rem;
    }

</style>