<template>
  <div class="col-3 m-auto">
        <select class="form-select" v-model="selectedValue" @click="$emit('choosedGenre', selectedValue)">
            <option value="">Nessuna selezione</option>
            <option>Jazz</option>
            <option>Rock</option>
            <option>Pop</option>
            <option>Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'searchComponent',
    data: function(){
        return{
            selectedValue: '',
        }
    }

}
</script>

<style>

</style>