<template>
  <div>
    <select class="form-select" aria-label="Default select example">
        <option selected>Open this select menu</option>
        <option v-for="genre,i in genreList" :key="i" value="1">{{genre}}</option>
    </select>
  </div>
</template>

<script>
export default {
name: "MainSelect",
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
    e se il genere non esiste lio pushiamo
 */