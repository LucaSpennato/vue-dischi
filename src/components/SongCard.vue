<template>

  <div class="card ms_card col-2 p-0" >
    <div class="card-body">
        <img class="img-fluid" src="https://img.discogs.com/vknPDdrqRbT92pNRX0W4I5N91jg=/fit-in/300x300/filters:strip_icc():format(jpeg):mode_rgb():quality(40)/discogs-images/R-1246953-1448927086-6590.jpeg.jpg" alt="ciao">
        <h5 class="card-title text-light my-3">Card title</h5>
        <h5 class="card-subtitle text-muted fs-6">Card title</h5>
        <h6 class="card-subtitle mb-2 text-muted fs-6">Card subtitle</h6>
    </div>
  </div>

</template>

<script>
export default {
  name: "SongCard",
};
</script>

<style lang="scss">
    @import '../style/variables.scss';

    div.ms_card{
        background-color: $cardbgColor;
    }

</style>