<template>
<div>
  <MainSelect :genreList="genreList" @GenreSelection="FilterCard"></MainSelect>
  <div class="my_container">
      <MainCard 
      v-for="character,i in characterList" :key="i"
      :poster="character.poster"
      :title="character.title"
      :author="character.author"
      :year="character.year" 
      :genre="character.genre">
      </MainCard>
  </div>
</div>
</template>

<script>

import axios from "axios"
import MainCard from "./MainCard.vue"
import MainSelect from "./MainSelect.vue"


export default {
name: "Main",
data(){
    return{
        characterList:"",
        genreList:"",

    }
},

components:{ MainCard, MainSelect },

mounted(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then(resp => {
      this.characterList=(resp.data.response)

    }),
     axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then(resp => {
      let arr = ""
      arr=(resp.data.response.map(function (el) {return el.genre}))
      this.genreList=[...new Set(arr)]
    })
  },
methods:{
  FilterCard(genreSelected){
    console.log(genreSelected);
    //this.characterList.filter(genreSelected)
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then(resp => {
      this.characterList=(resp.data.response.filter( function (el) {return el.genre.includes(genreSelected)}))
      
      //console.log(resp.data.response.map( function (el) {return el.genre}));
      console.log(resp.data.response.filter( function (el) {return el.genre.includes(genreSelected)}));
   })
    

  }
}

}
</script>

<style lang="scss" scoped>
    .my_container{
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        background-color: rgba(25,45,59,255);
        gap: 30px;
        padding: 30px 0;
        min-height:80vh ;
    }
</style>