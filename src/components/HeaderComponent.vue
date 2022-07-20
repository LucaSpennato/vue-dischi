<template>
  <header>
    <div class="container-fluid">
        <div class="row align-items-center justify-content-between">
            <div class="col-1 text-center py-3">
                <img class="w-50" src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png" alt="">
            </div>
            <div class="col-3">
              <select class="form-select" v-model="selectedValue" @click="$emit('choosedGenre', selectedValue)">
                        <option value="">Nessuna selezione</option>
                        <option>Jazz</option>
                        <option>Rock</option>
                        <option>Pop</option>
                        <option>Metal</option>
                  </select>
            </div>
        </div>
    </div>

  </header>
</template>

<script>
export default {
  name: 'HeaderComponent',
  data: function(){
    return{
      selectedValue: '',
    }
  }
}
</script>

<style lang="scss">
  @import '../style/variables.scss';

  header{
    height: 5rem;
    background-color: $headerPrimBgColor;
  }

</style>