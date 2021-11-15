<template>
  <div class="container">
      <MainCard 
        :poster="character.poster"
        :title="character.title"
        :author="character.author"
        :year="character.year" 
        v-for="character,i in characterList" :key="i" >
        </MainCard>
  </div>
</template>

<script>

import MainCard from "./MainCard.vue"
import axios from "axios"


export default {
name: "Main",
data(){
    return{
        characterList:[]
    }
},
components:{ MainCard },
mounted(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then(resp => {
      this.characterList.push(...resp.data.response)

    })
  }

}
</script>

<style lang="scss" scoped>
    .container{
        display: flex;
        flex-wrap: wrap;
        background-color: rgba(25,45,59,255);
    }
</style>