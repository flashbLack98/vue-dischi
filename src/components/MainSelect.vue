<template>
  <div>
    <select v-model="selectGenre" @change="$emit('GenreSelection', selectGenre)" class="form-select w-25 mt-5" aria-label="Default select example">
        <option selected value="">All</option>
        <option v-for="genre,i in genreList" :key="i" :value="genre">{{genre}}</option>
    </select>
  </div>
</template>

<script>
export default {
name: "MainSelect",
data(){
    return{
        selectGenre: ""
    }
},
props:[ "genreList" ]

}
</script>

<style lang="scss" scoped>
div{
    background-color: rgba(25,45,59,255);
    display: flex;
    justify-content: center;
}
</style>

/*  fare un array vuoto dei generi da mettere nel select
    controlliamo il genere delle carte
    e se il genere non esiste lo pushiamo
 */