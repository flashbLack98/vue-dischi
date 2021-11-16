<template>
  <div class="card">
      <div class="img_container"><img :src="poster" alt=""></div>
      <h3>{{ title }}</h3>
      <p>{{ author }}</p>
      <p>{{ year }}</p>
  </div>
</template>

<script>


export default {
name:"MainCard",
props: ["poster", "title", "author", "year"]
}
</script>

<style lang="scss" scoped>
.card{
    width: calc(100% / 5 - 5px);
    height: 300px;
    background-color: rgba(43,58,70,255);
    display: flex;
    flex-direction: column;
    align-content: center;
    margin: 50px 10px;
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
        margin: 0;
    }
    p{
        text-align: center;
        padding: 0 5px;
    }
}
</style>