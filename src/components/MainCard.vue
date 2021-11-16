<template>
  <div class="my_card">
      <div class="img_container"><img :src="poster" alt=""></div>
      <h3 class=" m-0">{{ title }}</h3>
      <p class=" m-0">{{ author }}</p>
      <p class=" m-0">{{ year }}</p>

  </div>
</template>

<script>


export default {
name:"MainCard",
props: ["poster", "title", "author", "year" , "genre"],

}
</script>

<style lang="scss" scoped>
.my_card{
    width: calc(100% / 5 - 30px);
    height: 300px;
    background-color: rgba(43,58,70,255);
    display: flex;
    flex-direction: column;
    .img_container{
        width: 100px;
        height: 100px;
        margin: 10px auto;
        img{
            height: 100%;
            width: 100%;
            object-fit: cover;
        }
    }
    h3{
        text-align: center;
    }
    p{
        text-align: center;
    }
}
</style>

/*  se il select è rock 
    allora stampa solo le carte rock
 */
