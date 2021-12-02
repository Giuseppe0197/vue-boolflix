<template>
  <div class="series">
    
    <div class="imgThumbCont">

      <img :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`" class="imgThumb">

    </div>

    <div class="infoSeries">

      <h3 class="titleSeries">Titolo della serie: {{serie.name}}</h3>

      <h3>Titolo originale: {{serie.original_name}}</h3>

      <img v-if="serie.original_language === 'en'" src="../assets/Flag_of_the_United_Kingdom.png" alt="" class="imgFlag">

      <img v-else-if="serie.original_language === 'it'" src="../assets/italian_flag.jpg" alt="" class="imgFlag">
      
      <h3 v-else>La lingua originale non disponibile</h3>

      <h3>Voto Generale: {{serie.vote_average / 2}}</h3>

    </div>

  </div>
</template>

<script>


export default {
  name: 'SeriesSubComp',
  props: {
    serie: Object
  }
}
</script>

<style lang="scss">
.series {
    margin-left: 30px;
    width: calc(100% / 4 - 10px);
    margin: 10px 5px;
    border: 3px solid black;
    color: red;

    .imgThumb{
      width: 100%;
    }

    span {
      font-weight: bold;
      font-size: 18px;
    }

    .imgFlag {
        width: 20px;
        margin-top: 15px;
    }

    h3 {
        margin-top: 15px;
    }
}

</style>
