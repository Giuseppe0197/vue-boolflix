<template>
  <div class="films">
    
    <div class="imgThumbCont">

      <img :src="`https://image.tmdb.org/t/p/w342${details.poster_path}`" class="imgThumb">

    </div>

    <div class="infoFilm">

      <h3 class="titleFilm">Titolo del Film: {{details.title}}</h3>

      <h3>Titolo originale: {{details.original_title}}</h3>

      <img v-if="details.original_language === 'en'" src="../assets/Flag_of_the_United_Kingdom.png" alt="" class="imgFlag">

      <img v-else-if="details.original_language === 'it'" src="../assets/italian_flag.jpg" alt="" class="imgFlag">
      
      <h3 v-else>La lingua originale non disponibile</h3>

      <!-- <h3>{{details.original_language}}</h3> -->

      <h3>Voto Generale: {{details.vote_average / 2}}</h3>

    </div>



      

  </div>
</template>

<script>


export default {
  name: 'FilmSubComp',
  props: {
    details: Object
  }
}
</script>

<style lang="scss">

.films {
    margin-left: 30px;
    width: calc(100% / 4 - 10px);
    margin: 10px 5px;
    border: 3px solid black;
    color: red;

    /* .imgThumbCont:hover{
      display: none;
    } */

    .imgThumb{
      width: 100%;
    }

    /* .imgThumb:hover {
      display: none;
    }

    .infoFilm {
      display: none;
    }

    .imgThumb:hover .infoFilm {
      display: block;
    } */

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
