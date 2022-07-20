<template>
        <div class="col-3  m-auto">
            <h3>Scegli per autore</h3>
            <select class="form-select" v-model="selectedValue" @click="$emit('choosedGenre', selectedValue)">
                <option value="">Nessuna selezione</option>
                <option>Queen</option>
                <option>Bon Jovi</option>
                <option>Sting</option>
                <option>Steve Gadd Band</option>
                <option>Iron Maiden</option>
                <option>Eric Clapton</option>
                <option>Deep Purple</option>
                <option>Metallica</option>
                <option>Dave Weckl</option>
                <option>Michael jacjson</option>
                
            </select>
        </div>
</template>

<script>
export default {
    name: 'searchForAuthor',
    data: function(){
        return{
            selectedValue: '',
        }
    }

}
</script>

<style>

</style>